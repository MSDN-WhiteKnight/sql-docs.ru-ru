---
description: sp_cursorclose (Transact-SQL)
title: sp_cursorclose (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursor_close_TSQL
- sp_cursor_close
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cursorclose
ms.assetid: d9b7b44d-cdff-456e-97df-7031a3b9beb6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 0363b69839d6cf58eebaa0394a591050c3443cd6
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89536652"
---
# <a name="sp_cursorclose-transact-sql"></a>sp_cursorclose (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Закрывает и размещает курсор, а также освобождает все связанные ресурсы; то есть удаляется временная таблица, используемая для поддержки ключевого набора ключей или статического **курсора**. sp_cursorclose вызывается путем указания ID = 9 в пакете потока табличных данных (TDS).  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_cursorclose cursor  
```  
  
## <a name="arguments"></a>Аргументы  
 *курсор*  
 Значение *обработчика* курсора, созданное [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и возвращаемое процедурой sp_cursoropen. *cursor* является обязательным параметром, который вызывает входное значение **int** .  
  
> [!NOTE]  
>  Входное значение -1 относится ко всем курсорам в текущем соединении.  
  
## <a name="remarks"></a>Примечания  
 *курсор* возвратит сообщения об ошибках, если процедура была выполнена после закрытия курсора или если указан недопустимый маркер.  
  
 Состояние RPC обозначает общий успех или общий неуспех.  
  
 Счетчик строк DONE всегда равен 0.  
  
## <a name="see-also"></a>См. также  
 [sp_cursoropen &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-cursoropen-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
