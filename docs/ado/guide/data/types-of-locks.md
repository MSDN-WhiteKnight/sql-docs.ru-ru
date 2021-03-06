---
description: Типы блокировок
title: Типы блокировок | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- AdLockBatchOptimistic [ADO]
- AdLockReadOnly [ADO]
- AdLockUnspecified [ADO]
- locks [ADO], types
- AdLockOptimistic [ADO]
- AdLockPessimistic [ADO]
ms.assetid: 12a978c0-b8a0-4ef0-87f0-a43c13659272
author: rothja
ms.author: jroth
ms.openlocfilehash: 55087e96c0855f24153dee9bc279d9abf58d3f04
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "88979265"
---
# <a name="types-of-locks"></a>Типы блокировок
## <a name="adlockbatchoptimistic"></a>адлоккбатчоптимистик  
 Обозначает обновления оптимистических пакетов. Требуется для режима пакетного обновления.  
  
 Многие приложения одновременно получают несколько строк, а затем нуждаются в согласованных обновлениях, включающих в себя весь набор строк для вставки, обновления или удаления. При использовании пакетных курсоров требуется только один цикл обработки на сервере, что повышает производительность обновления и снижает сетевой трафик. С помощью библиотеки курсоров пакетной службы можно создать статический курсор, а затем отключиться от источника данных. На этом этапе можно внести изменения в строки, а затем повторно подключиться и опубликовать изменения в источнике данных в пакете.  
  
## <a name="adlockoptimistic"></a>adLockOptimistic  
 Указывает, что поставщик использует записи блокировки оптимистической блокировки только при вызове метода **Update** . Это означает, что существует вероятность, что другой пользователь может изменить данные между моментом изменения записи и при вызове **Update**, который создает конфликты. Используйте этот тип блокировки в ситуациях, когда вероятность конфликта мала или если конфликты можно легко устранить.  
  
## <a name="adlockpessimistic"></a>адлоккпессимистик  
 Указывает пессимистическую блокировку, запись по записям. Поставщик выполняет необходимые действия, чтобы обеспечить успешное редактирование записей, как правило, путем блокировки записей в источнике данных непосредственно перед редактированием. Конечно, это означает, что после начала редактирования записи недоступны другим пользователям, пока блокировка не будет освобождена путем вызова **Update.** Используйте этот тип блокировки в системе, где нельзя позволить себе одновременно вносить изменения в данные, например в систему резервирования.  
  
## <a name="adlockreadonly"></a>адлоккреадонли  
 Указывает записи, которые доступны только для чтения. Изменить данные нельзя. Блокировка только для чтения — это "самый быстрый" тип блокировки, так как не требует от сервера поддержки блокировки записей.  
  
## <a name="adlockunspecified"></a>адлоккунспеЦифиед  
 Не указывает тип блокировки.
