---
description: Таблицы резервного копирования и восстановления (Transact-SQL)
title: Таблицы резервного копирования и восстановления (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- system tables [SQL Server], backup tables
- backup system tables [SQL Server]
- system tables [SQL Server], restore tables
- restore system tables [SQL Server]
ms.assetid: aa615add-54e6-40f5-8b55-3728b26884ee
author: markingmyname
ms.author: maghan
ms.openlocfilehash: abb69d6cefa270330a41d90bea0352981dd7ee8a
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89540985"
---
# <a name="backup-and-restore-tables-transact-sql"></a>Таблицы резервного копирования и восстановления (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Подразделы данного раздела описывают системные таблицы, которые хранят сведения, необходимые для операций резервного копирования и восстановления базы данных.  
  
## <a name="in-this-section"></a>В этом разделе  
 [backupfile;](../../relational-databases/system-tables/backupfile-transact-sql.md)  
 Содержит по одной строке для всех данных или файла журнала базы данных.  
  
 [backupfilegroup](../../relational-databases/system-tables/backupfilegroup-transact-sql.md)  
 Содержит по одной строке для каждой файловой группы во время резервного копирования.  
  
 [backupmediafamily;](../../relational-databases/system-tables/backupmediafamily-transact-sql.md)  
 Содержит по одной строке для каждого семейства носителей.  
  
 [backupmediaset;](../../relational-databases/system-tables/backupmediaset-transact-sql.md)  
 Содержит по одной строке для каждого резервного набора носителей.  
  
 [backupset;](../../relational-databases/system-tables/backupset-transact-sql.md)  
 Содержит по одной строке для каждого резервного набора данных.  
  
 [logmarkhistory](../../relational-databases/system-tables/logmarkhistory-transact-sql.md)  
 Содержит одну строку для каждой зафиксированной помеченной транзакции.  
  
 [restorefile;](../../relational-databases/system-tables/restorefile-transact-sql.md)  
 Содержит по одной строке для каждого восстановленного файла. Включены и файлы, восстановленные неявно по имени файловой группы.  
  
 [restorefilegroup;](../../relational-databases/system-tables/restorefilegroup-transact-sql.md)  
 Содержит по одной строке для каждой восстановленной файловой группы.  
  
 [restorehistory.](../../relational-databases/system-tables/restorehistory-transact-sql.md)  
 Содержит по одной строке для каждой операции восстановления.  
  
 [suspect_pages](../../relational-databases/system-tables/suspect-pages-transact-sql.md)  
 Содержит одну строку на таблицу, возвратившую ошибку с кодом 824 (с ограничением в 1000 строк).  
  
 [sysopentapes](../../relational-databases/system-tables/sysopentapes-transact-sql.md)  
 Содержит по одной строке для каждого из открытых ленточных устройств.  
  
  
