---
description: IBM DB2 Subscribers
title: Подписчики IBM DB2 | Документация Майкрософт
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, IBM DB2
- data types [SQL Server replication], non-SQL Server Subscribers
- IBM DB2 Subscribers
- mapping data types [SQL Server replication]
- heterogeneous Subscribers, IBM DB2
ms.assetid: a1a27b1e-45dd-4d7d-b6c0-2b608ed175f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e044fa0e368893f0aaa1fe8175b306c2fc04c24b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88327070"
---
# <a name="ibm-db2-subscribers"></a>IBM DB2 Subscribers
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддерживает принудительные подписки на IBM DB2/AS 400, DB2/MVS и DB2/Universal Database через поставщики OLE DB, включенные в состав [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Host Integration Server.  
  
## <a name="configuring-an-ibm-db2-subscriber"></a>Настройка подписчика IBM DB2  
 Чтобы настроить подписчик IBM DB2, выполните следующие шаги:  
  
1.  Установите последнюю версию поставщика [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB для DB2 на распространитель:  
  
    -   Если вы используете выпуск [!INCLUDE[ssNoVersion_md](../../../includes/ssnoversion-md.md)] Enterprise Edition, на веб-странице [загрузок SQL Server](https://go.microsoft.com/fwlink/?LinkId=149256) в разделе **связанных файлов для загрузки** щелкните ссылку, чтобы скачать последнюю версию пакета дополнительных компонентов Microsoft SQL Server. На веб-странице с **пакетом дополнительных компонентов Microsoft SQL Server** найдите раздел **Поставщик Microsoft OLE DB для DB2**.  
  
    -   Если вы используете выпуск [!INCLUDE[ssNoVersion_md](../../../includes/ssnoversion-md.md)] Standard Edition, установите последнюю версию сервера служб [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Host [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] (HIS), содержащего этот поставщик.  
  
     В дополнение к установке поставщика рекомендуется установить средство доступа к данным, которое применяется на следующем шаге (оно устанавливается по умолчанию вместе с загрузкой [!INCLUDE[ssNoVersion_md](../../../includes/ssnoversion-md.md)] Enterprise Edition). Дополнительные сведения об установке и использовании инструмента доступа к данным см. в документации поставщика или в документации по HIS.  
  
2.  Создайте строку соединения для подписчика. Строку соединения можно создавать в любом текстовом редакторе, однако рекомендуется использовать средство доступа к данным. Чтобы создать строку с помощью средства доступа к данным, выполните следующие действия:  
  
    1.  Нажмите кнопку **Пуск**, последовательно выберите **Программы**, **Поставщик Microsoft OLE DB для DB2**, а затем выберите **Средство доступа к данным**.  
  
    2.  В диалоговом окне **Средство доступа к данным**выполните шаги, чтобы указать сведения о сервере DB2. После завершения работы с средством доступа к данным создается универсальная связь данных (UDL, universal data link) со связанной строкой соединения (в отличие от строки соединения, UDL не используется репликацией).  
  
    3.  Доступ к строке подключения: щелкните узел UDL правой кнопкой мыши в инструменте доступа к данным и выберите **Показать строку подключения**.  
  
     Строка соединения будет аналогична следующей строке (разрывы строк добавлены для удобочитаемости):  
  
    ```  
    Provider=DB2OLEDB;Initial Catalog=MY_SUBSCRIBER_DB;Network Transport Library=TCP;Host CCSID=1252;  
    PC Code Page=1252;Network Address=MY_SUBSCRIBER;Network Port=50000;Package Collection=MY_PKGCOL;  
    Default Schema=MY_SCHEMA;Process Binary as Character=False;Derive Parameters=False;Units of Work=RUW;DBMS Platform=DB2/NT;  
    Persist Security Info=False;Connection Pooling=True;  
    ```  
  
     Большинство параметров в строке уникальны для настраиваемого сервера DB2, но для параметров `Process Binary as Character` и `Derive Parameters` всегда должно быть задано значение `False`. Параметр `Initial Catalog` должен иметь значение для идентификации базы данных подписки. Если создается подписка, строка соединения вводится в мастер создания подписки.  
  
3.  Создайте публикацию моментальных снимков или публикацию транзакций, активируйте ее для подписчиков, отличных от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , а затем создайте принудительную подписку для подписчика. Дополнительные сведения см. в статье [Создание подписки для подписчика, отличного от подписчика SQL Server](../../../relational-databases/replication/create-a-subscription-for-a-non-sql-server-subscriber.md).  
  
4.  При желании можно указать пользовательский скрипт создания для одной или более статей. После публикации таблицы для нее создается скрипт `CREATE TABLE`. Для подписчиков, отличных от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , скрипт создается на разновидности языка [!INCLUDE[tsql](../../../includes/tsql-md.md)] , а затем перед применением к подписчику преобразуется агентом распространителя в более универсальную разновидность SQL. Чтобы указать пользовательский скрипт создания, измените существующий скрипт [!INCLUDE[tsql](../../../includes/tsql-md.md)] или создайте полный скрипт, который использует разновидность языка DB2 SQL. Если создается скрипт DB2, используйте директиву **bypass_translation** , чтобы агент распространителя применил скрипт к подписчику без трансляции.  
  
     Сценарии могут изменяться по множеству причин, но наиболее распространенной причиной является изменение сопоставлений типов данных. Дополнительные сведения см. в подразделе «Вопросы сопоставления типов данных» этого раздела. При изменении скрипта [!INCLUDE[tsql](../../../includes/tsql-md.md)] изменения следует ограничивать сопоставлениями типов данных (кроме того, скрипт не должен содержать никаких комментариев). Если требуются более существенные изменения, создайте скрипт DB2.  
  
     **Изменение скрипта статьи и предоставление его в качестве пользовательского скрипта создания**  
  
    1.  После создания моментального снимка для публикации перейдите к папке моментальных снимков для публикации.  
  
    2.  Найдите файл `.sch` с тем же именем, что и у статьи, например `MyArticle.sch`.  
  
    3.  Откройте этот файл в Блокноте или в другом текстовом редакторе.  
  
    4.  Измените файл и сохраните его в другом каталоге.  
  
    5.  Выполните хранимую процедуру `sp_changearticle`, указав путь к файлу и имя свойства *creation_script* . Дополнительные сведения см. в статье [sp_changearticle (Transact-SQL)](../../../relational-databases/system-stored-procedures/sp-changearticle-transact-sql.md).  
  
     **Создание скрипта статьи и предоставление его в качестве пользовательского скрипта создания**  
  
    1.  Создайте скрипт статьи, используя разновидность языка DB2 SQL. Убедитесь, что первой строкой файла является **bypass_translation**, и строка не содержит больше ничего, кроме этого.  
  
    2.  Выполните хранимую процедуру sp_changearticle, указав путь к файлу и имя свойства *creation_script*.  
  
## <a name="considerations-for-ibm-db2-subscribers"></a>Рекомендации для подписчиков IBM DB2  
 В дополнение к рекомендациям, приведенным в разделе [Non-SQL Server Subscribers](../../../relational-databases/replication/non-sql/non-sql-server-subscribers.md), при репликации на подписчики DB2 рассмотрите следующие вопросы:  
  
-   Данные и индексы для каждой реплицированной таблицы назначаются табличному пространству DB2. Размер страницы табличного пространства DB2 управляет максимальным количеством столбцов и максимальным размером строк таблиц, принадлежащих табличному пространству. Основываясь на количестве реплицированных столбцов и максимальном размере строк таблиц, убедитесь, что используется подходящее табличное пространство, связанное с реплицированными таблицами.  
  
-   Не публикуйте таблицы для подписчиков DB2 с использованием репликации транзакций, если один или более первичных ключевых столбцов в таблице относится к типу данных DECIMAL(32-38, 0-38) или NUMERIC(32-38, 0-38). Репликация транзакций идентифицирует строки, используя первичный ключ, что может привести к сбою, так как эти типы данных сопоставлены с VARCHAR(41) на подписчике. Таблицы с первичными ключами, которые используют эти типы данных, могут публиковаться с помощью репликации моментальных снимков.  
  
-   Если хотите предварительно создать таблицы на подписчике вместо того, чтобы они были созданы репликацией, используйте параметр только поддержка репликации. Дополнительные сведения см. в статье [Инициализация подписки на публикацию транзакций без моментального снимка](../../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md).  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] допускает наличие более длинных имен таблиц и столбцов, чем DB2:  
  
    -   Если база данных публикации содержит таблицы с именами длиннее, чем имена, поддерживаемые на подписчике версией DB2, укажите альтернативное имя для свойства статьи destination_table. Дополнительные сведения об установке свойств во время создания публикации см. в статье, посвященной [созданию публикации на SQL Server 2016](../../../relational-databases/replication/publish/create-a-publication.md), а также в статье об [определении статьи](../../../relational-databases/replication/publish/define-an-article.md).  
  
    -   Невозможно указать альтернативные имена столбцов. Обязательно убедитесь, что опубликованные таблицы не содержат имена столбцов более длинные, чем имена, поддерживаемые на подписчике версией DB2.  
  
## <a name="mapping-data-types-from-sql-server-to-ibm-db2"></a>Сопоставление типов данных SQL Server с типами данных IBM DB2  
 Следующая таблица показывает сопоставления типов данных, применяемых во время репликации данных на подписчик, использующий IBM DB2.  
  
|Тип данных SQL Server|Тип данных IBM DB2|  
|--------------------------|-----------------------|  
|**bigint**|DECIMAL(19,0)|  
|**binary(1-254)**|CHAR(1-254) FOR BIT DATA|  
|**binary(255-8000)**|VARCHAR(255-8000) FOR BIT DATA|  
|**bit**|SMALLINT|  
|**CHAR(1-254)**|CHAR(1-254)|  
|**char(255-8000)**|VARCHAR(255-8000)|  
|**date**|DATE|  
|**datetime**|timestamp|  
|**datetime2(0-7)**|VARCHAR(27)|  
|**datetimeoffset(0-7)**|VARCHAR(34)|  
|**decimal(1-31, 0-31)**|DECIMAL(1-31, 0-31)|  
|**decimal(32-38, 0-38)**|VARCHAR(41)|  
|**float(53)**|DOUBLE|  
|**float**|FLOAT|  
|**geography**|IMAGE|  
|**geometry**|IMAGE|  
|**hierarchyid**|IMAGE|  
|**image**|VARCHAR(0) FOR BIT DATA*|  
|**into**|INT|  
|**money**|DECIMAL(19,4)|  
|**nchar(1-4000)**|VARCHAR(1-4000)|  
|**ntext**|VARCHAR(0)*|  
|**numeric(1-31, 0-31)**|DECIMAL(1-31,0-31)|  
|**numeric(32-38, 0-38)**|VARCHAR(41)|  
|**nvarchar(1-4000)**|VARCHAR(1-4000)|  
|**nvarchar(max)**|VARCHAR(0)*|  
|**real**|ВЕЩЕСТВЕННОЕ ЧИСЛО|  
|**smalldatetime**|timestamp|  
|**smallint**|SMALLINT|  
|**smallmoney**|DECIMAL(10,4)|  
|**sql_variant**|Недоступно|  
|**sysname**|VARCHAR(128)|  
|**text**|VARCHAR(0)*|  
|**time(0-7)**|VARCHAR(16)|  
|**timestamp**|CHAR(8) FOR BIT DATA|  
|**tinyint**|SMALLINT|  
|**uniqueidentifier**|CHAR(38)|  
|**varbinary(1-8000)**|VARCHAR(1-8000) FOR BIT DATA|  
|**varchar(1-8000)**|VARCHAR(1-8000)|  
|**varbinary(max)**|VARCHAR(0) FOR BIT DATA*|  
|**varchar(max)**|VARCHAR(0)*|  
|**xml**|VARCHAR(0)*|  
  
* Дополнительные сведения о сопоставлениях с VARCHAR(0) см. в разделе ниже.  
  
### <a name="data-type-mapping-considerations"></a>Вопросы сопоставления типов данных  
 При репликации на подписчики DB2 учтите следующие вопросы сопоставления типов данных:  
  
-   При сопоставлении типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **char**, **varchar**, **binary** и **varbinary** с типами данных DB2 CHAR, VARCHAR, CHAR FOR BIT DATA и VARCHAR FOR BIT DATA (соответственно) репликация задает для типа данных DB2 такую же длину, что и для типа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
     Это позволяет успешно создавать таблицы на подписчике до тех пор, пока ограничение размера страницы DB2 достаточно велико, чтобы вместить максимальный размер строки. Убедитесь, что имя входа, используемое для доступа к базе данных DB2, имеет разрешения на доступ к табличным пространствам достаточного размера для таблиц, реплицируемых в DB2.  
  
-   DB2 может поддерживать столбцы типа VARCHAR размером до 32 килобайт (КБ), поэтому некоторые столбцы больших объектов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] могут соответствующим образом сопоставляться со столбцами DB2 типа VARCHAR. Однако поставщик OLE DB, используемый репликацией для DB2, не поддерживает сопоставление больших объектов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с большими объектами DB2. По этой причине столбцы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **text**, **varchar(max)**, **ntext** и **nvarchar(max)** в создаваемых скриптах сопоставляются с типом VARCHAR(0). Значение длины 0 должно меняться на соответствующее значение до применения скрипта к подписчику. Если длина типа данных не изменяется, то при попытке создания таблицы на подписчике DB2 возникает ошибка 604 (ошибка 604 указывает на недопустимую точность или длину атрибута типа данных).  
  
     На основе своих знаний исходной реплицируемой таблицы определите, подходит ли она для сопоставления большого объекта [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с элементом DB2 переменной длины, и укажите соответствующую максимальную длину в пользовательском скрипте создания. Сведения об указании пользовательского скрипта создания см. в описании шага 5 в подразделе «Настройка подписчика IBM DB2» данного раздела.  
  
    > [!NOTE]  
    >  Длина, указанная для типа DB2, при объединении с другими длинами столбцов не может превышать максимальный размер строки, основанный на табличном пространстве DB2, которому назначены табличные данные.  
  
     Если не существует соответствующего сопоставления для столбца больших объектов, рассмотрите возможность использования фильтрации для статьи, чтобы столбец не реплицировался. Дополнительные сведения см. в статье [Фильтрация опубликованных данных](../../../relational-databases/replication/publish/filter-published-data.md).  
  
-   При репликации типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **nchar** и **nvarchar** в типы данных DB2 CHAR и VARCHAR для типа DB2 используется та же спецификация длины, что и для типа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Однако длина типа данных может быть слишком мала для созданной таблицы DB2.  
  
     В некоторых средах DB2 элемент данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **char** не ограничивается однобайтовыми символами. Это следует учитывать при анализе размера элемента типа CHAR или VARCHAR. Следует также принять во внимание символы *shift in* (сдвиг внутрь) и *shift out* (сдвиг наружу), если в них есть необходимость. При репликации таблиц со столбцами **nchar** и **nvarchar** , возможно, потребуется увеличить максимальную длину для типа данных в пользовательском скрипте создания. Сведения об указании пользовательского скрипта создания см. в описании шага 5 в подразделе «Настройка подписчика IBM DB2» данного раздела.  
  
## <a name="see-also"></a>См. также  
 [Non-SQL Server Subscribers](../../../relational-databases/replication/non-sql/non-sql-server-subscribers.md)   
 [Подписка на публикации](../../../relational-databases/replication/subscribe-to-publications.md)  
  
  
