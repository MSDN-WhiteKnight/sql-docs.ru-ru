---
description: FilterGroupEnum
title: Филтерграупенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- FilterGroupEnum
helpviewer_keywords:
- FilterGroupEnum enumeration [ADO]
ms.assetid: b22e725e-84bd-4286-a070-290c278c3783
author: rothja
ms.author: jroth
ms.openlocfilehash: 1d9fdf420ee3b550bebfe394bf6722623307384a
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "88972995"
---
# <a name="filtergroupenum"></a>FilterGroupEnum
Указывает группу записей для фильтрации из [набора записей](./recordset-object-ado.md).  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adFilterAffectedRecords**|2|Фильтры для просмотра только тех записей, на которые повлияли последние операции [удаления](./delete-method-ado-recordset.md), повторной [синхронизации](./resync-method.md), [UpdateBatch](./updatebatch-method.md)или [CancelBatch](./cancelbatch-method-ado.md) .|  
|**адфилтерконфликтингрекордс**|5|Фильтры для просмотра записей, которые не прошли Последнее обновление пакета.|  
|**adFilterFetchedRecords**|3|Фильтры для просмотра записей в текущем кэше, то есть результатов последнего вызова для получения записей из базы данных.|  
|**адфилтерноне**|0|Удаляет текущий фильтр и восстанавливает все записи для просмотра.|  
|**адфилтерпендингрекордс**|1|Фильтры для просмотра только тех записей, которые были изменены, но еще не отправлены на сервер. Применяется только для режима пакетного обновления.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Филтерграуп. АФФЕКТЕДРЕКОРДС|  
|Адоенумс. Филтерграуп. КОНФЛИКТИНГРЕКОРДС|  
|Адоенумс. Филтерграуп. ФЕТЧЕДРЕКОРДС|  
|Адоенумс. Филтерграуп. NONE|  
|Адоенумс. Филтерграуп. ПЕНДИНГРЕКОРДС|  
  
## <a name="applies-to"></a>Применение  
 [Свойство Filter](./filter-property.md)