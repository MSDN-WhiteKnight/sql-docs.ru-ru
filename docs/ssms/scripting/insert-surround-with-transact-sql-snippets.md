---
title: Вставка фрагментов кода окружения Transact-SQL
description: Узнайте, как вставить фрагмент кода окружения, который служит отправной точкой для размещения инструкций в блоках кода.
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- snippets [Transact-SQL], surround with
- IntelliSense [SQL Server], surround with snippets
- Transact-SQL snippets, surround with
ms.assetid: 5b5a8c6c-968e-4361-a7f5-9e2ac186d927
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: e7596e6ef216682ad66695b30712b3e77e2aa5ab
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92039001"
---
# <a name="insert-surround-with-transact-sql-snippets"></a>Вставка фрагментов кода окружения Transact-SQL
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
  Внутри фрагмента кода находится шаблон, который можно использовать в качестве начальной точки при включении инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] в блоки BEGIN, IF или WHILE.  
  
## <a name="inserting-surround-with-snippets"></a>Вставка фрагментов кода окружения  
 Фрагменты кода окружения могут быть запущены одним из трех способов: с помощью сочетания клавиш, через меню **Правка** и через контекстное меню.  
  
 После вставки фрагмента кода необходимо заменить текст замены, образовав правильную инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] . Дополнительные сведения см. в разделе [Завершение фрагментов кода Transact-SQL](./complete-transact-sql-snippets.md).  
  
#### <a name="to-insert-a-surround-with-snippet"></a>Вставка фрагментов кода окружения  
  
1.  В окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] выберите набор инструкций, который нужно включить в блок.  
  
2.  Используйте один из трех способов для отображения списка фрагментов кода окружения:  
  
    -   Нажмите сочетание клавиш CTRL+K, CTRL+S.  
  
    -   В меню **Правка** укажите **IntelliSense**и выберите команду **Заключить в** .  
  
    -   Щелкните правой кнопки мыши выделенный текст и выберите команду **Заключить в** в контекстном меню.  
  
3.  Выберите имя фрагмента кода (BEGIN, IF или WHILE) из списка, используя мышь, или введите имя фрагмента кода и нажмите клавишу TAB или ВВОД.  
  
## <a name="see-also"></a>См. также:  
 [Вставка фрагментов кода Transact-SQL](./insert-transact-sql-snippets.md)  
  
