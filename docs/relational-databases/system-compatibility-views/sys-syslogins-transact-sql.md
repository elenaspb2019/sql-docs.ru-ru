---
title: sys.sysимена входа (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 09/08/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syslogins_TSQL
- syslogins
- sys.syslogins
- sys.syslogins_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.syslogins compatibility view
- syslogins system table
ms.assetid: 4cb34f17-a4bb-469f-a218-71f074e6308f
author: rothja
ms.author: jroth
ms.openlocfilehash: eb1fd5b8dcf9867cb61452534a742cc929a41396
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891941"
---
# <a name="syssyslogins-transact-sql"></a>sys.syslogins (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждой учетной записи входа.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
**Применимо к**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ( [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] с по [текущей версии](https://go.microsoft.com/fwlink/p/?LinkId=299658)).  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**sid**|**varbinary(85)**|Идентификатор защиты.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**креатедате**|**datetime**|Дата добавления имени входа.|  
|**updatedate**|**datetime**|Дата обновления имени входа.|  
|**accdate**|**datetime**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**totcpu**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**totio**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**spacelimit**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**тимелимит**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**resultlimit**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**name**|**sysname**|Имя входа пользователя.|  
|**dbname**|**sysname**|Имя базы данных по умолчанию для пользователя при установлении соединения.|  
|**password**|**nvarchar(128)**|Возвращает значение NULL.|  
|**language**|**sysname**|Язык по умолчанию для пользователя.|  
|**denylogin**|**int**|1 = Имя входа принадлежит пользователю или группе [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, и ему отказано в доступе.|  
|**hasaccess**|**int**|1 = Имени входа разрешен доступ на сервер.|  
|**isntname**|**int**|1 = Имя входа принадлежит пользователю или группе Windows.<br /><br /> 0 = Имя входа является именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**иснтграуп**|**int**|1 = Имя входа принадлежит группе Windows.|  
|**isntuser**|**int**|1 = Имя входа принадлежит пользователю Windows.|  
|**sysadmin**|**int**|1 = имя входа является членом роли сервера **sysadmin** .|  
|**securityadmin**|**int**|1 = имя входа является членом роли сервера **администратора** .|  
|**serveradmin**|**int**|1 = имя входа является членом предопределенной роли сервера **serveradmin** .|  
|**setupadmin**|**int**|1 = имя входа является членом предопределенной роли сервера **setupadmin** .|  
|**processadmin**|**int**|1 = имя входа является членом предопределенной роли сервера **processadmin** .|  
|**diskadmin**|**int**|1 = имя входа является членом предопределенной роли сервера **diskadmin** .|  
|**dbcreator**|**int**|1 = имя входа является членом предопределенной роли сервера **dbcreator** .|  
|**bulkadmin**|**int**|1 = имя входа является членом предопределенной роли сервера **bulkadmin** .|  
|**LoginName**|**nvarchar(128)**|Имя входа пользователя. Предоставляется для обратной совместимости.|  
  
## <a name="see-also"></a>См. также  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
