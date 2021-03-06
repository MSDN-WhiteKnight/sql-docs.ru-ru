---
description: Свойства предупреждения — создание предупреждения (страница "Параметры")
title: Свойства предупреждения — создание предупреждения (страница "Параметры")
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql13.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: bf0e3d57a0d759f45634cf06dd1d54c4b22d014b
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92036664"
---
# <a name="alert-properties---new-alert-options-page"></a>Свойства предупреждения — создание предупреждения (страница "Параметры")
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

> [!IMPORTANT]  
> В [Управляемом экземпляре Azure SQL](/azure/sql-database/sql-database-managed-instance) в настоящее время поддерживается большинство функций агента SQL Server (но не все). Подробные сведения см. в статье [Различия в T-SQL между Управляемым экземпляром SQL Azure и SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

На этой странице можно просматривать и изменять параметры оповещений агента [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  

## <a name="options"></a>Параметры  
**Электронная почта**  
Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые по электронной почте.  
  
**Пейджер**  
Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые на пейджер.  
  
**Команда Net send**  
Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые службой net send.  
  
**Дополнительное сообщение уведомления**  
Введите любой дополнительный текст для включения в уведомления.  
  
**Задержка между ответами**  
Укажите время задержки между повторными наступлениями события. Некоторые события могут происходить часто в течение короткого периода времени. В таком случае, вероятно, необходимо будет узнать о наступлении события, но не обязательно, чтобы для каждого события выдавался ответ. Используйте этот параметр для указания лимита времени ожидания. При наличии задержки после того, как предупреждение отвечает на событие, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выжидает в течение указанного времени задержки прежде, чем ответить снова, независимо от того, происходит ли событие во время ожидания.  
  
**Минуты**  
Укажите задержку в минутах. Для ответа при каждом наступлении события укажите 0 минут и 0 секунд.  
  
**Секунды**  
Укажите задержку в секундах. Для ответа при каждом наступлении события укажите 0 минут и 0 секунд.  
  
## <a name="see-also"></a>См. также:  
[Оповещения](../../ssms/agent/alerts.md)  
