---
description: Параметры атрибутов с предысторией (мастер медленно изменяющихся измерений)
title: Параметры атрибутов с предысторией (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9610a734543c9199e54d3f8489d86e03089f10ed
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88430706"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a>Параметры атрибутов с предысторией (мастер медленно изменяющихся измерений)

[!INCLUDE[sqlserver-ssis](../../../includes/applies-to-version/sqlserver-ssis.md)]


  Диалоговое окно **Параметры атрибутов с предысторией** используется для просмотра атрибутов с предысторией по дате начала и окончания, а также для записи атрибутов с предысторией в специально предназначенный для этого столбец.  
  
 Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](../../../integration-services/data-flow/transformations/slowly-changing-dimension-transformation.md).  
  
## <a name="options"></a>Параметры  
 **Использовать общий столбец для вывода текущих и устаревших записей**  
 Если выбрано отображение состояния атрибутов с предысторией в одном столбце, можно выбрать следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Столбец, указывающий текущую запись**|Выберите столбец, в котором указывается текущая запись.|  
|**Значение на момент актуальности**|Чтобы узнать, является ли запись текущей, выберите **True** или **Текущие** .|  
|**Значение для устаревшей записи**|Чтобы узнать, содержит ли запись значение предыстории, выберите **False** или **Устаревшие** .|  
  
 **Использовать данные о дате начала и окончания событий для идентификации текущих и устаревших записей**  
 Таблица измерения для этого параметра должна включать в себя столбец дат. Если выбрано отображение атрибутов с предысторией по датам начала и окончания, можно выбрать следующие параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Столбец, содержащий дату начала события**|Выберите в таблице измерения столбец, в котором находится дата начала.|  
|**Столбец, содержащий дату окончания события**|Выберите в таблице измерения столбец, в котором находится дата окончания.|  
|**Переменная для установки значений даты**|Выберите переменную даты из списка.|  
  
## <a name="see-also"></a>См. также:  
 [Настройка выходов при помощи мастера медленно изменяющихся измерений](../../../integration-services/data-flow/transformations/configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
