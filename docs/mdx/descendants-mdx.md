---
description: Descendants (многомерные выражения)
title: Потомки (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b883d1ce73a7259b285748e5a66f283a7d830424
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88491443"
---
# <a name="descendants-mdx"></a>Descendants (многомерные выражения)


  Возвращает набор потомков элемента на указанном уровне или расстоянии, по желанию включая или исключая потомков на других уровнях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Member expression syntax using a level expression  
Descendants(Member_Expression [ , Level_Expression [ ,Desc_Flag ] ] )  
  
Member expression syntax using a numeric expression  
Descendants(Member_Expression [ , Distance [ ,Desc_Flag ] ] )  
  
Set expression syntax using a level expression  
Descendants(Set_Expression [ , Level_Expression [ ,Desc_Flag ] ] )  
  
Member expression syntax using a numeric expression  
Descendants(Set_Expression [ , Distance [ ,Desc_Flag ] ] )  
  
```  
  
## <a name="arguments"></a>Аргументы  
 *Member_Expression*  
 Допустимое многомерное выражение, возвращающее элемент.  
  
 *Set_Expression*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Level_Expression*  
 Допустимое многомерное выражение, возвращающее уровень.  
  
 *Друг*  
 Допустимое числовое выражение, указывающее расстояние от заданного элемента.  
  
 *Desc_Flag*  
 Допустимая строка выражения, указывающая описание флага, коррелирующего с возможными наборами потомков.  
  
## <a name="remarks"></a>Комментарии  
 Если уровень указан, функция **Descendants** возвращает набор, содержащий потомки указанного элемента или элементов указанного набора на заданном уровне, при необходимости измененном с помощью флага, указанного в *Desc_Flag*.  
  
 Если задано значение *Distance* , функция **Descendants** возвращает набор, содержащий потомки указанного элемента или элементы указанного набора, которые являются заданным числом уровней вне иерархии указанного элемента, при необходимости измененном с помощью флага, указанного в *Desc_Flag*. Обычно эта функция используется с аргументом Distance для распределения неоднородных иерархий. Если заданное расстояние равно нулю, то функция возвращает набор, состоящий только из заданного элемента или заданного набора.  
  
 Если указано выражение набора, функция **Descendants** разрешается по отдельности для каждого элемента набора, а набор создается снова. Иными словами, синтаксис, используемый для функции **Descendants** , функционально эквивалентен функции [Generate](../mdx/generate-mdx.md) многомерные выражения.  
  
 Если уровень или расстояние не указаны, значение по умолчанию для уровня, используемого функцией, определяется путем вызова функции [Level](../mdx/level-mdx.md) (<\<Member>>. Level) для указанного элемента (если элемент указан) или путем вызова функции **уровня** для каждого элемента указанного набора (если задан набор). Если выражение уровня, расстояние и флаги не определены, то функция будет выполнена только в случае использования следующего синтаксиса:  
  
 `Descendants`  
  
 `(`  
  
 `Member_Expression ,`  
  
 `Member_Expression.Level ,`  
  
 `SELF_BEFORE_AFTER`  
  
 `)`  
  
 Если уровень определен, а описание флага не определено, то функция будет выполнена только в случае использования следующего синтаксиса:  
  
 `Descendants`  
  
 `(`  
  
 `Member_Expression ,`  
  
 `Level_Expression,`  
  
 `SELF`  
  
 `)`  
  
 Изменяя значение аргумента описания флага, можно включать или исключать на указанном уровне или расстоянии потомки, находящиеся до указанного уровня или расстояния (вплоть до конечных узлов) и после, а также конечные потомки независимо от указанного уровня или расстояния. В следующей таблице описаны флаги, разрешенные в аргументе *Desc_Flag* .  
  
|Flag|Описание|  
|----------|-----------------|  
|SELF|Возвращает только потомки заданного уровня или на заданном расстоянии. Функция включает в себя заданный элемент, если заданный уровень является уровнем заданного элемента.|  
|AFTER|Возвращает потомки со всех уровней, подчиненных уровню аргумента расстояния.|  
|BEFORE|Возвращает потомки элементов со всех уровней между заданным элементом и заданным уровнем или на заданном расстоянии. Включает в себя заданный элемент, но не включает элементы заданного уровня или расстояния.|  
|BEFORE_AND_AFTER|Возвращает потомки элементов со всех уровней, зависящих от заданного уровня или заданного элемента. Включает в себя заданный элемент, но не включает элементы заданного уровня или расстояния.|  
|SELF_AND_AFTER|Возвращает потомки элементов заданного уровня или расстояния и все уровни, зависящие от заданного уровня или расстояния.|  
|SELF_AND_BEFORE|Возвращает потомки заданного уровня или расстояния и со всех уровней между заданным элементом и заданным уровнем или на заданном расстоянии, включая заданный элемент.|  
|SELF_BEFORE_AFTER|Возвращает потомки со всех уровней, зависящих от уровня заданного элемента, и включает заданный элемент.|  
|LEAVES|Возвращает конечные потомки элементов между заданным элементом и заданным уровнем или на заданном расстоянии.|  
  
## <a name="examples"></a>Примеры  
 В следующем примере возвращается заданный элемент (США) и элементы между заданным элементом и элементами уровня, предшествующего заданному (City). В примере возвращаются сам заданный элемент (США) и элементы уровня State-Province (уровень перед уровнем City). Данный пример включает в себя комментарии к аргументам, что позволяет легко проверить другие аргументы для этой функции.  
  
```  
SELECT Descendants  
   ([Geography].[Geography].[Country].&[United States]  
      //, [Geography].[Geography].[Country]  
   , [Geography].[Geography].[City]  
      //, [Geography].[Geography].Levels (3)  
      //, SELF   
      //, AFTER  
      , BEFORE  
      // BEFORE_AND_AFTER  
      //, SELF_AND_AFTER  
      //, SELF_AND_BEFORE  
      //,SELF_BEFORE_AFTER  
      //,LEAVES   
   ) ON 0  
FROM [Adventure Works]   
```  
  
 В следующем примере возвращается ежедневное среднее значение `Measures.[Gross Profit Margin]` меры, вычисленное по дням каждого месяца в 2003 финансовом году из куба **Adventure Works** . Функция **Descendants** возвращает набор дней, определенных на основе текущего элемента `[Date].[Fiscal]` иерархии.  
  
```  
WITH MEMBER Measures.[Avg Gross Profit Margin] AS Avg  
   (  
      Descendants( [Date].[Fiscal].CurrentMember,   
           [Date].[Fiscal].[Date]  
          ),   
        Measures.[Gross Profit Margin]  
   )  
SELECT  
   Measures.[Avg Gross Profit Margin] ON COLUMNS,  
   [Date].[Fiscal].[Month].Members ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Fiscal Year].&[2003])  
```  
  
 В следующем примере используется выражение уровня и возвращается мера Internet Sales Amount для каждой административно-территориальной единицы (мера State-Province) Австралии (Australia), возвращается также процентное соотношение относительно общего значения Internet Sales Amount для каждой территории (State-Province). В этом примере используется функция Item для извлечения первого (и единственного) кортежа из набора, возвращаемого функцией- **предками** .  
  
```  
WITH MEMBER Measures.x AS   
   [Measures].[Internet Sales Amount] /   
   ( [Measures].[Internet Sales Amount],  
      Ancestors   
         ( [Customer].[Customer Geography].CurrentMember,   
           [Customer].[Customer Geography].[Country]  
         ).Item (0)  
   ), FORMAT_STRING = '0%'  
SELECT {[Measures].[Internet Sales Amount], Measures.x} ON 0,  
{Descendants   
   ( [Customer].[Customer Geography].[Country].&[Australia],   
     [Customer].[Customer Geography].[State-Province], SELF   
   )    
} ON 1  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по функциям многомерных выражений (многомерные выражения)](../mdx/mdx-function-reference-mdx.md)  
  
  
