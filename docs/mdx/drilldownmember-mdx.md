---
description: DrilldownMember (многомерные выражения)
title: DrilldownMember (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 0dfc26c52cbd478979cbbaad4a69e66bc58138a5
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "92194026"
---
# <a name="drilldownmember-mdx"></a>DrilldownMember (многомерные выражения)


  Детализирует углублением элементы указанного набора, присутствующие во втором указанном наборе.  
  
 Эта функция может также детализировать углублением набор кортежей с использованием первой иерархии кортежей или дополнительно указанной иерархии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DrillDownMember(<Set_Expression1>, <Set_Expression2> [,[<Target_Hierarchy>]] [,[RECURSIVE][,INCLUDE_CALC_MEMBERS]])  
```  
  
## <a name="arguments"></a>Аргументы  
 *Set_Expression1*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Set_Expression2*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Target_Hierarchy*  
 Допустимое многомерное выражение, возвращающее иерархию.  
  
 *Рекурсивного*  
 Ключевое слово, которое обозначает рекурсивное сравнение наборов.  
  
 *Include_Calc_Members*  
 Ключевое слово, позволяющее включать вычисляемые элементы в результаты углубленной детализации.  
  
## <a name="remarks"></a>Remarks  
 Эта функция возвращает набор дочерних элементов, упорядоченных по иерархии, который включает элементы, указанные в первом наборе, которые также присутствуют во втором наборе. Детализация родительских элементов не производится, если первый набор содержит родительский элемент и один или несколько дочерних элементов. Первый набор может иметь любую размерность, но второй набор должен быть одномерным. Порядок следования исходных элементов первого набора сохраняется, однако все дочерние элементы, входящие в результирующий набор функции, следуют непосредственно за своим родительским элементом. Функция создает результирующий набор, извлекая потомков каждого элемента первого набора, присутствующих во втором наборе. Если указан параметр **recursive** , функция по-своему рекурсивно сравнивает элементы результирующего набора со вторым набором, получая дочерние элементы для каждого элемента результирующего набора, который также имеется во втором наборе, пока все элементы из результирующего набора не будут найдены во втором наборе.  
  
 Запрос свойства XMLA **мдпропмдксдриллфунктионс** позволяет проверить уровень поддержки, предоставляемый сервером для функций сверления; Дополнительные сведения см. в разделе [Поддерживаемые свойства xmla &#40;&#41;XMLA ](/analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) .  
  
 Первый набор может содержать кортежи вместо элементов. Углубленная детализация кортежей является расширением OLE DB и возвращает набор кортежей вместо набора элементов.  
  
> [!IMPORTANT]  
>  Детализация элемента не производится, если непосредственно за ним следует один из его дочерних элементов. Порядок элементов в наборе важен для семейств функций углубленной детализации * и обобщением \* .  
  
## <a name="examples"></a>Примеры  
 В следующем примере выполняется детализация углублением первого элемента Australia, являющегося элементом первого набора, который также присутствует во втором наборе.  
  
```  
SELECT DrilldownMember   
   ( [Geography].[Geography].Children,  
      {[Geography].[Geography].[Country].[Australia],  
        [Geography].[Geography].[State-Province].[New South Wales]}  
   )  
   ON 0  
   FROM [Adventure Works]  
```  
  
 В следующем примере выполняется детализация углублением первого элемента Australia, являющегося элементом первого набора, который также присутствует во втором наборе. Тем не менее, поскольку указан аргумент RECURSIVE, функция продолжает рекурсивно сравнивать элементы результирующего набора (элементы уровня State-Province) со вторым набором, получая потомков каждого элемента результирующего набора (элементы уровня города), присутствующих во втором наборе, до тех пор, пока в результирующем наборе больше нельзя будет найти элементы, присутствующие во втором наборе.  
  
```  
SELECT DrilldownMember   
   ( [Geography].[Geography].Children,  
      {[Geography].[Geography].[Country].[Australia],  
        [Geography].[Geography].[State-Province].[New South Wales]}  
   ,RECURSIVE)  
   ON 0  
   FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>См. также:  
 [Справочник по функциям многомерных выражений (многомерные выражения)](../mdx/mdx-function-reference-mdx.md)  
  
