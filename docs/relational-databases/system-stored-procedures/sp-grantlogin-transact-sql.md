---
title: sp_grantlogin (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_grantlogin_TSQL
- sp_grantlogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_grantlogin
ms.assetid: 0c873d99-c3bf-4eb1-948b-a46cb235ccd4
ms.author: vanto
author: VanMSFT
ms.openlocfilehash: de02d84d781c5db2d86902034b500c6b4a02ea2f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891808"
---
# <a name="sp_grantlogin-transact-sql"></a>sp_grantlogin (Transact-SQL)

[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Создает имя входа на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]Вместо этого используйте [CREATE LOGIN](../../t-sql/statements/create-login-transact-sql.md) .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
sp_grantlogin [@loginame=] 'login'  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @loginame = ] 'login'`Имя пользователя или группы Windows. Имя пользователя или группы Windows должно быть дополнено именем домена Windows в форме "пользователь *домена*" \\ *User*, например **London\Joeb**. Аргумент *Login* имеет тип **sysname**и не имеет значения по умолчанию.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="remarks"></a>Комментарии  
 **sp_grantlogin** вызывает создание имени входа, которое поддерживает дополнительные параметры. Сведения о создании SQL Serverных имен входа см. в разделе [Create login &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)  
  
 **sp_grantlogin** не может быть выполнена в пользовательской транзакции.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение ALTER ANY LOGIN на сервере.  
  
## <a name="examples"></a>Примеры  
 В следующем примере используется `CREATE LOGIN` для создания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени входа для пользователя Windows `Corporate\BobJ.` . это предпочтительный метод.  
  
```sql
CREATE LOGIN [Corporate\BobJ] FROM WINDOWS;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры безопасности &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [Создание имени входа &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
