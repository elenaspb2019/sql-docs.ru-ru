---
title: managed_backup. sp_set_parameter (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_set_parameter_TSQL
- sp_set_parameter
- smart_admin.sp_set_parameter
- smart_admin.sp_set_parameter_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_set_parameter
- smart_admin.sp_set_parameter
ms.assetid: bd8ae5fd-1337-4b7f-b0a4-153cbca9fa5f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3eab417e1d959c990e53aca3119546a73a3e1aad
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052920"
---
# <a name="managed_backupsp_set_parameter-transact-sql"></a>managed_backup. sp_set_parameter (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Задает значение указанного системного параметра Smart Admin.  
  
 Доступные параметры связаны с [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]. Эти параметры используются для задания уведомлений по электронной почте, включения определенных расширенных событий и предоставления разрешения пользователю задавать политики управления на основе политик. Необходимо указать пары имени параметра и значения параметра.  

  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
EXEC managed_backup.sp_set_parameter   
    [@parameter_name = ] {'SSMBackup2WANotificationEmailIds' | 'SSMBackup2WAEnableUserDefinedPolicy' | 'SSMBackup2WADebugXevent' | 'FileRetentionDebugXevent' | 'StorageOperationDebugXevent'}  
    ,[@parameter_value = ] 'parameter_value'  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a>Даваемых  
 @parameter_name  
 Имя параметра, для которого требуется установить значение. @parameter_nameимеет тип NVARCHAR (128). Допустимые имена параметров: **SSMBackup2WANotificationEmailIds**, **SSMBackup2WADebugXevent**, **SSMBackup2WAEnableUserDefinedPolicy**, **филеретентиондебугксевент**и **сторажеоператиондебугксевент**.  
  
 @parameter_value  
 Задаваемое значение параметра. @parameterзначение равно NVARCHAR (128).  Ниже приведены разрешенные пары имен и значений параметров.  
  
-   @parameter_name= ' SSMBackup2WANotificationEmailIds ': @parameter_value = ' Email '  
  
-   @parameter_name= ' SSMBackup2WAEnableUserDefinedPolicy ': @parameter_value = {' true ' | "false"}  
  
-   @parameter_name= ' SSMBackup2WADebugXevent ': @parameter_value = {' true ' | "false"}  
  
-   @parameter_name= ' Филеретентиондебугксевент ': @parameter_value = {' true ' | "false"}  
  
-   @parameter_name= ' Сторажеоператиондебугксевент ' = {' true ' | "false"}  
  
## <a name="return-code-value"></a>Значения кодов возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="best-practices"></a>Рекомендации  
 Необязательный раздел, описывающий рекомендации по выполнению инструкции или процедуры.  
  
## <a name="security"></a>Безопасность  
  
### <a name="permissions"></a>Разрешения  
 Требуются разрешения **EXECUTE** на хранимую процедуру **managed_backup. sp_set_parameter** .  
  
## <a name="examples"></a>Примеры  
 Следующие примеры включают оперативные и отладочные расширенные события.  
  
```  
-- to enable operational events  
Use msdb;  
Go  
         EXEC managed_backup.sp_set_parameter 'FileRetentionOperationalXevent', 'True'  
--  to enable debug events  
Use msdb;  
Go  
         EXEC managed_backup.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
```  
  
 Следующий пример включает уведомления об ошибках и предупреждения по электронной почте, а также устанавливает emailID для отправки уведомлений.  
  
```  
Use msdb  
Go  
EXEC managed_backup.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'  
  
```  
  
  
