---
title: Перезапуск прерванного восстановления (Transact-SQL)
description: В этом примере показано, как перезапустить прерванную операцию восстановления в SQL Server с помощью Transact-SQL.
ms.custom: seo-lt-2019
ms.date: 12/17/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- interrupted restore operation
- restoring databases [SQL Server], restarting interrupted operation
- resetting options changed after backup
- database restores [SQL Server], restarting interrupted operation
- restarting interrupted restore operation
- restoring interrupted operation [SQL Server]
ms.assetid: 6413a07d-fd90-448d-8f29-12c5a1972618
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bfe32215d30b6722a621b0ebb3f0f556a34ddf26
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85669582"
---
# <a name="restart-an-interrupted-restore-operation-transact-sql"></a>Перезапуск прерванной операции восстановления (язык Transact-SQL)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  В этом разделе объясняется, как перезапустить прерванную операцию восстановления.  
  
### <a name="to-restart-an-interrupted-restore-operation"></a>Перезапуск прерванной операции восстановления  
  
1.  Инициируйте прерванную операцию RESTORE еще раз, указав следующую информацию.  
  
    -   Те же предложения, которые были использованы в первоначальной инструкции RESTORE.  
  
    -   Предложение RESTART.  
  
## <a name="example"></a>Пример  
 Следующий программный код перезапускает прерванную операцию восстановления:  
  
```sql  
-- Restore a full database backup of the AdventureWorks database.  
RESTORE DATABASE AdventureWorks  
   FROM DISK = 'C:\AdventureWorks.bck'  
GO  
-- The restore operation halted prematurely.  
-- Repeat the original RESTORE statement specifying WITH RESTART.  
RESTORE DATABASE AdventureWorks   
   FROM DISK = 'C:\AdventureWorks.bck'  
   WITH RESTART  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Выполнение полного восстановления базы данных (модель полного восстановления)](../../relational-databases/backup-restore/complete-database-restores-full-recovery-model.md)   
 [Выполнение полного восстановления базы данных (простая модель восстановления)](../../relational-databases/backup-restore/complete-database-restores-simple-recovery-model.md)   
 [RESTORE (Transact-SQL)](../../t-sql/statements/restore-statements-transact-sql.md)  
  
  
