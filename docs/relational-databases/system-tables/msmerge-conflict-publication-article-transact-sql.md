---
title: MSmerge_conflict_publication_article (T-SQL)
description: Описывает MSmerge_conflict_publication_article хранимую процедуру, которая содержит сведения о строках с конфликтующими или измененными строками, которые были отменены для достижения конвергенции данных.
ms.custom: seo-lt-2019
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSmerge_conflict_publication_article_TSQL
- MSmerge_conflict_publication_article
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_conflict_publication_article system table
ms.assetid: dc4490b4-02d8-4dfc-98f5-0cf8de8e11be
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 17f6d7920589e4797369f96d69727fa21917cc00
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89545709"
---
# <a name="msmerge_conflict_publication_article-transact-sql"></a>MSmerge_conflict_publication_article (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSmerge_conflict_publication_articleная** таблица содержит сведения о строках, которые были изменены или были отменены для достижения конвергенции данных. Для каждой реплицируемой таблицы в публикации существует таблица конфликтов, при этом к имени таблицы конфликтов добавляется имя публикации и имя статьи. Таблицы конфликтов по статьям расположены в базе данных, которая используется для занесения в журнал конфликтов; обычно ею является база данных публикации, однако при децентрализованном занесении в журнал конфликтов ею может быть и база данных подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**_\_имя столбца \_ статьи_**|**variable**|Представляет столбец в реплицируемой таблице. В данной системной таблице содержится по одному столбцу на каждый столбец статьи таблицы.|  
|**уникаль**|**uniqueidentifier**|Идентификатор строки конфликта.|  
|**ModifiedDate**|**datetime**|Время возникновения конфликта.|  
|**\_идентификатор источника DataSource \_**|**uniqueidentifier**|Подписка, для которой изменение строк было отменено или конфликт был потерян.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
