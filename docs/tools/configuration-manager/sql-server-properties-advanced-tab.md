---
title: Свойства SQL Server (вкладка «Дополнительно»)
description: Узнайте о параметрах на вкладке "Дополнительно" диалогового окна свойств SQL Server, таких как путь к данным, идентификатор экземпляра и пользовательские свойства.
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 2ffd10fd-bac1-478f-9cff-96ed6c8b787f
author: markingmyname
ms.author: maghan
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
ms.openlocfilehash: 2acca0bd84985700395cb3d073e6476167577b68
ms.sourcegitcommit: 6d53ecfdc463914f045c20eda96da39dec22acca
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88901176"
---
# <a name="sql-server-properties-advanced-tab"></a>Свойства SQL Server (вкладка «Дополнительно»)
[!INCLUDE [SQL Server Windows Only - ASDBMI ](../../includes/applies-to-version/sql-windows-only-asdbmi.md)]
  По умолчанию на вкладке **Дополнительно** присутствуют следующие свойства. Если определены пользовательские свойства, они также отображаются на этой вкладке вместе со значениями.  
  
## <a name="options"></a>Параметры  
 **Кластеризованный**  
 Указывает, установлена ли эта служба в качестве ресурса кластеризованного сервера.  
  
 **Передача отзывов пользователей**  
 Указывает, был ли запущен контроль качества обслуживания для этой службы. Дополнительные сведения о передаче отзывов пользователей см. в разделе «Настройки параметров отчета об ошибках» электронной документации.  
  
 **Путь к данным**  
 Отображает путь к двоичным файлам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для установленной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 **Каталог дампа**  
 Отображает расположение дампа памяти в случае возникновения ошибки.  
  
 **Отчет об ошибках**  
 Если установлено значение **Да**, то в случае возникновения серьезного сбоя программа "Доктор Ватсон» направит сведения либо в [!INCLUDE[msCoName](../../includes/msconame-md.md)], либо на сервер ошибок. Дополнительные сведения по отчетам об ошибках см. в разделе «Настройки параметров отчета об ошибках» электронной документации. Чтобы изменить это значение, в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] щелкните сервер правой кнопкой мыши, выберите пункт **Свойства** и перейдите на страницу **Прочие параметры сервера**. Параметры находятся в области **Информационный отчет** .  
  
 **Версия файла**  
 Отображает версию исполняемого объекта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Путь установки**  
 Отображает путь к двоичным файлам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для установленной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 **Идентификатор экземпляра**  
 Указывает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующий эту службу.  
  
 **Язык**  
 Отображает установленный по умолчанию язык для сообщений сервера.  
  
 **Корневая папка реестра**  
 Отображает расположение разделов реестра, используемых этим приложением.  
  
 **Версия пакета обновления**  
 Отображает версию пакета обновления для этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 **Номер SKU**  
 Отображает номер SKU продукта, иногда называемый выпуском продукта.  
  
 **Параметры запуска**  
 Указывает все параметры запуска, используемые этим экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Параметры разделяются точками с запятой. Параметры по умолчанию включают пути к файлу данных главной базы данных (`master.mdf`), файлу журнала главной базы данных (`mastlog.ldf`) и файлу журнала ошибок. Дополнительные сведения о синтаксисе параметров запуска см. в разделе **Использование параметров запуска службы SQL Server**электронной документации.  
  
 **Номер SKU**  
 Отображает номер SKU продукта.  
  
 **Версия**  
 Отображает номер версии этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 **Имя виртуального сервера**  
 **Имя виртуального сервера** , когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] установлен на кластеризованный сервер.  
  
  
