---
title: Сопоставление типов данных XSD с типами данных XPath (SQLXML)
description: Сведения о том, как сопоставлять типы данных XSD с типами данных XPath при выполнении запроса XPath в SQLXML 4,0.
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- XPath queries [SQLXML], mapping data types
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XPath data types [SQLXML]
- XSD schemas [SQLXML], mapping data types
ms.assetid: ced1a95e-18d4-4a5a-8da8-dbb6d58bbd45
author: MightyPen
ms.author: genemi
ms.reviewer: ''
ms.custom: seo-lt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 4bc4f771d2afaefa3e214008c59c6200ebd29549
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85764926"
---
# <a name="mapping-xsd-data-types-to-xpath-data-types-sqlxml-40"></a>Сопоставление типов данных XSD с типами данных XPath (SQLXML 4.0)
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  При выполнении запроса XPath к схеме XSD и указании типа XSD в атрибуте **xsd: Type** XPath использует тип данных, указанный при обработке запроса.  
  
 Тип данных XPath для узла выводится из типа данных XSD в схеме, как показано в следующей таблице. (Узел EmployeeID используется в демонстрационных целях.)  
  
|Тип данных XSD|Тип данных XDR|Эквивалентный<br /><br /> тип данных XPath|SQL Server<br /><br /> преобразование не используется|  
|-------------------|-------------------|------------------------------------|--------------------------------------------|  
|**Base64Binary**<br /><br /> **HexBinary**|**None**<br /><br /> **bin. base64bin. hex**|**Неприменимо**|Отсутствуют<br /><br /> EmployeeID|  
|**Boolean**|**boolean**|**boolean**|CONVERT(bit, EmployeeID)|  
|**Decimal, Integer, float, Byte, Short, int, Long, float, Double, Унсигнедбите, Унсигнедшорт, unsignedInt, Унсигнедлонг**|**number, int, float,i1, i2, i4, i8,r4, r8ui1, ui2, ui4, ui8**|**number**|CONVERT(float(53), EmployeeID)|  
|**ID, IDREF, идрефсентити, сущности, нотация, NMTOKEN, NMTOKENS, DateTime, String, AnyURI**|**ID, IDREF, идрефсентити, сущности, перечисление, нотация, NMTOKEN, NMTOKENS, char, dateTime, dateTime.tz, String, URI, UUID**|**string**|CONVERT(nvarchar(4000), EmployeeID, 126)|  
|**decimal**|**fixed14.4**|**Неприменимо (в XPath отсутствует тип данных, эквивалентный фиксированному типу данных XDR 14,4.)**|CONVERT(money, EmployeeID)|  
|**date**|**date**|**string**|LEFT(CONVERT(nvarchar(4000), EmployeeID, 126), 10)|  
|**time**|**time**<br /><br /> **time.tz**|**string**|SUBSTRING(CONVERT(nvarchar(4000), EmployeeID, 126), 1 + CHARINDEX(N'T', CONVERT(nvarchar(4000), EmployeeID, 126)), 24)|  
  
  
