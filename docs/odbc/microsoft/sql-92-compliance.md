---
description: Соответствие SQL-92
title: Соответствие требованиям SQL-92 | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Jet-based ODBC drivers [ODBC], SQL-92 compliance
- desktop database drivers [ODBC], SQL-92 compliance
- SQL-92 compliance [ODBC]
- ODBC desktop database drivers [ODBC], SQL-92 compliance
ms.assetid: 50c8c7df-df01-4f4d-ad62-d059cf29d73a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7d978b236c45d442732cd3602c3fbbb6d16dfd8f
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88483437"
---
# <a name="sql-92-compliance"></a>Соответствие SQL-92
Драйверы ODBC для настольных систем и базовый модуль Microsoft Jet не соответствуют SQL-92. Они поддерживают множество функций, определенных в SQL-92. Некоторые функции, поддерживаемые в драйвере, не поддерживаются в SQL-92. Дополнительные сведения см. в *статье Microsoft Jet ядро СУБД программиста*. Ниже приведены основные различия между ними.  
  
-   SQL, используемый драйверами баз данных для настольных систем, поддерживает больше мощных выражений, чем указано в SQL-92.  
  
-   К предикату BETWEEN применяются различные правила.  
  
-   SQL, используемый драйверами баз данных для настольных систем и ANSI SQL, поддерживает различные ключевые слова.  
  
 Следующие функции SQL-92 не поддерживаются в Microsoft Jet SQL:  
  
-   Инструкции по обеспечению безопасности, такие как GRANT и LOCK.  
  
-   DISTINCT с ссылками на агрегатные функции.  
  
 Следующие функции являются усовершенствованиями в SQL, используемыми драйверами баз данных для настольных систем, которые не указаны в SQL-92:  
  
-   Инструкция TRANSFORM обеспечивает поддержку перекрестных запросов.  
  
-   Дополнительные агрегатные функции (**STDEV** и **ДИСПР**).  
  
> [!NOTE]  
>  Драйверы базы данных для настольных систем поддерживают стандартный синтаксис ANSI для% (Percent) и _ (символ подчеркивания), а не * (звездочка) и? (вопросительный знак).
