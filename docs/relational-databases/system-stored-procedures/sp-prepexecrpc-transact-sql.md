---
description: sp_prepexecrpc (Transact-SQL)
title: sp_prepexecrpc (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursor_prepexecrpc
- sp_cursor_prepexecrpc_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_prepexecrpc
ms.assetid: 35d686f2-ef31-4eaa-baa9-9cef5d6c87c2
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 9db0c4450f6726d39934afac27c3306dae9ded3f
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89535027"
---
# <a name="sp_prepexecrpc-transact-sql"></a>sp_prepexecrpc (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Подготавливает и вызывает параметризованную хранимую процедуру, заданную с помощью идентификатора RPC. sp_prepexecrpc вызывается по ID = 14 в пакете потока табличных данных (TDS).  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_prepexecrpc handle OUTPUT, RPCCall  
    [ , bound_param ] [ ,...n]]  
```  
  
## <a name="arguments"></a>Аргументы  
 *справиться*  
 Сформированный системой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентификатор подготовленного дескриптора. *Handle* является обязательным параметром с возвращаемым значением **int** .  
  
 *рпккалл*  
 Определяет вызов хранимой процедуры с использованием канонического синтаксиса ODBC. *Рпккалл* — это обязательный параметр, который вызывает входное строковое значение типа **ntext** .  
  
 *bound_param*  
 Означает необязательное использование дополнительных параметров. *bound_param* вызывает входное значение любого типа данных для обозначения дополнительных используемых параметров.  
  
## <a name="see-also"></a>См. также  
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
