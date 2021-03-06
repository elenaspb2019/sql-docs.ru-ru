---
title: sys.pdw_replicated_table_cache_state (Transact-SQL)
ms.custom: seo-dt-2019
ms.date: 07/03/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
author: ronortloff
ms.author: rortloff
monikerRange: = azure-sqldw-latest || = sqlallproducts-allversions
ms.openlocfilehash: 6fa3c064a2fb54d474afee9cbd4d20c878ff1893
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87394039"
---
# <a name="syspdw_replicated_table_cache_state-transact-sql"></a>sys.pdw_replicated_table_cache_state (Transact-SQL)
[!INCLUDE [asa](../../includes/applies-to-version/asa.md)]

  Возвращает состояние кэша, связанного с реплицированной таблицей **object_id**.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|object_id|**int**|Идентификатор объекта для таблицы. См. статью [sys. objects &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).<br /><br /> **object_id** является ключом для этого представления.||  
|state|**nvarchar(40)**|Состояние кэша реплицированной таблицы для этой таблицы.|"NotReady", "Ready"|  
  
## <a name="example"></a>Пример
В этом примере показано соединение sys. pdw_replicated_table_cache_state с sys. tables для получения имени таблицы и состояния кэша реплицированной таблицы.

```sql
SELECT t.[name], p.[object_id], p.[state]
  FROM sys.pdw_replicated_table_cache_state p 
  JOIN sys.tables t ON t.object_id = p.object_id
```



## <a name="next-steps"></a>Дальнейшие действия  
 Список всех представлений каталога для хранилища данных SQL и параллельного хранилища данных см. в статье [представления каталога данных SQL и параллельного](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)хранилища данных.   
  
