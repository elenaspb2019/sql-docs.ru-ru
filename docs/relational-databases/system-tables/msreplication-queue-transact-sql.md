---
title: MSreplication_queue (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSreplication_queue
- MSreplication_queue_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSreplication_queue system table
ms.assetid: 664bf817-8021-4417-96d6-2bb1e4baabff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3bdbfed403a8b85a195134e053a151905efa128f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889419"
---
# <a name="msreplication_queue-transact-sql"></a>MSreplication_queue (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSreplication_queue** используется процессом репликации для хранения команд в очереди, выданных всеми обновляемыми посредством очередей подписками, использующими очередь на основе SQL. Эта таблица хранится в базе данных подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**publisher**|**sysname**|Имя издателя.|  
|**publisher_db**|**sysname**|Имя базы данных публикации.|  
|**публикации**|**sysname**|Имя публикации.|  
|**транид**|**sysname**|Идентификатор транзакции, в которой была выполнена команда из очереди.|  
|**данные**|**varbinary(8000)**|Упакованный поток байтов, содержащий сведения об отложенных командах.|  
|**datalen**|**int**|Длина данных параметра в байтах.|  
|**CommandType**|**int**|Тип отложенной команды:<br /><br /> 1 = пользовательская команда в транзакции.<br /><br /> 2 = команда синхронизации подписки.|  
|**insertdate**|**datetime**|Дата вставки.|  
|**orderkey**|**bigint**|Столбец идентификаторов, постепенно увеличивающийся.|  
|**cmdstate**|**bit**|Состояние команды:<br /><br /> 0 = завершена.<br /><br /> 1 = частично.|  
  
## <a name="see-also"></a>См. также  
 [Таблицы репликации &#40;&#41;Transact-SQL](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
