---
description: удаление заданий
title: удаление заданий
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 2fd58cfc92b1d80578ed2d15d63fae5eedd00b94
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92038010"
---
# <a name="delete-jobs"></a>удаление заданий
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> В [Управляемом экземпляре Azure SQL](/azure/sql-database/sql-database-managed-instance) в настоящее время поддерживается большинство функций агента SQL Server (но не все). Подробные сведения см. в статье [Различия в T-SQL между Управляемым экземпляром SQL Azure и SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

Задание — это определенная последовательность действий, выполняемых агентом SQL Server. По умолчанию после завершения выполнения задания не удаляются. Можно удалить одно или несколько заданий агента [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , независимо от успешности завершения задания. В агенте [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] также можно настроить автоматическое удаление заданий в случае их успешного выполнения, сбоя или завершения.  
  
По умолчанию для удаления задания члены предопределенной роли сервера **sysadmin** могут выполнять хранимую системную процедуру [sp_delete_job (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-delete-job-transact-sql.md) . Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
Дополнительные сведения о разрешениях этих ролей см. в разделе [Предопределенные роли базы данных агента SQL Server](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
Члены предопределенной роли сервера **sysadmin** с помощью процедуры **sp_delete_job** могут удалить любое задание. Пользователь, который не является членом предопределенной роли сервера **sysadmin** , может удалять только задания, принадлежащие этому пользователю.  
  
## <a name="related-tasks"></a>Связанные задачи  
  
|Описание|Раздел|  
|-|-|   
|Описывает, как удалить одно или несколько заданий агента [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|[Удаление одного или нескольких заданий](../../ssms/agent/delete-one-or-more-jobs.md)|  
|Описывает, как настроить автоматическое удаление заданий агента [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в случае их успешного выполнения, сбоя или завершения.|[Автоматическое удаление задания](../../ssms/agent/automatically-delete-a-job.md)|  
