---
title: sys. database_credentials (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 02/27/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.database_credentials
- sys.database_credentials_TSQL
- database_credentials
- database_credentials_TSQL
helpviewer_keywords:
- sys.database_credentials catalog view
ms.assetid: 796322df-e62a-45bf-b519-89e1d521abce
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5b78875b7c6f3440bd747045d1b90d0f8ef323c4
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87394889"
---
# <a name="sysdatabase_credentials-transact-sql"></a>sys. database_credentials (Transact-SQL)
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

  Возвращает по одной строке для каждого учетного данных области базы данных в базе данных.  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]Вместо этого используйте представление [sys. database_scoped_credentials](../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md) .    
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|credential_id|**int**|Идентификатор учетных данных области базы данных. Уникален в базе данных.|  
|name|**sysname**|Имя учетных данных области базы данных. Уникален в базе данных.|  
|credential_identity|**nvarchar(4000)**|Имя применяемого идентификатора. Обычно это пользователь Windows. Это имя не обязательно должно быть уникальным.|  
|create_date|**datetime**|Время создания учетных данных области базы данных.|  
|modify_date|**datetime**|Время последнего изменения учетных данных области базы данных.|  
|target_type|**nvarchar (100)**|Тип учетных данных области базы данных. Возвращает значение NULL для учетных данных области базы данных.|  
|target_id|**int**|Идентификатор объекта, с которым сопоставлены учетные данные области базы данных. Возвращает 0 для учетных данных области базы данных|  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение `CONTROL` на базу данных.  
  
## <a name="see-also"></a>См. также  
 [Учетные данные &#40;ядро СУБД&#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [Создание УЧЕТных данных с областью действия базы данных &#40;&#41;Transact-SQL](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
 [ИЗМЕНЕНИЕ УЧЕТных данных с областью действия базы данных &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-credential-transact-sql.md)   
 [УДАЛИТЬ УЧЕТные данные области базы данных &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-scoped-credential-transact-sql.md)   
 [CREATE CREDENTIAL (Transact-SQL)](../../t-sql/statements/create-credential-transact-sql.md)   
 [sys.credentials (Transact-SQL)](../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md)  
  
  
