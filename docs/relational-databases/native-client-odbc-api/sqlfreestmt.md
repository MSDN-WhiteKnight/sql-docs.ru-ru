---
description: Функция SQLFreeStmt
title: SQLFreeStmt | Документация Майкрософт
ms.custom: ''
ms.date: 11/23/2015
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLFreeStmt function
ms.assetid: d9666d0b-3446-480e-bf1a-10b01213e411
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 2a131178ecef5a9a0e04eb1b0564f89e6788d745
ms.sourcegitcommit: 04cf7905fa32e0a9a44575a6f9641d9a2e5ac0f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91811110"
---
# <a name="sqlfreestmt"></a>Функция SQLFreeStmt
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Обычно   
      Не рекомендуется применять функцию**SQLFreeStmt** в ODBC 3.0 и более поздних версиях. Однако если приложению необходимо повторно использовать инструкцию, необходимо по-прежнему использовать **SQLFreeStmt** с параметрами **SQL_RESET_PARAMS** и **SQL_UNBIND** ). Вы также можете использовать [SQLCloseCursor](../../relational-databases/native-client-odbc-api/sqlclosecursor.md), [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md), [SQLBindCol](../../relational-databases/native-client-odbc-api/sqlbindcol.md), [SQLSetDescField](../../relational-databases/native-client-odbc-api/sqlsetdescfield.md)и [SQLFreeHandle](../../relational-databases/native-client-odbc-api/sqlfreehandle.md) для замены или дублирования функции **SQLFreeStmt** и использовать их вместо них.  
  
 Как правило, более эффективно использовать инструкции, чем удалять их и выделять новые. Однако в некоторых ситуациях, например при повторном использовании инструкций, SQLFreeStmt все равно необходимо использовать.  
  
## <a name="see-also"></a>См. также:  
 [Функция SQLFreeStmt](../../odbc/reference/syntax/sqlfreestmt-function.md)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
