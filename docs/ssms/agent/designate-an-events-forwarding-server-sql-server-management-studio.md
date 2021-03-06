---
title: Назначение сервера пересылки событий
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: d05b8e386a3df5314433dbf505e3c7682740434c
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85749049"
---
# <a name="designate-an-events-forwarding-server"></a>Назначение сервера пересылки событий
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> Сейчас в [управляемом экземпляре базы данных SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) поддерживается большинство функций агента SQL Server (но не все). Подробные сведения см. в статье [Различия T-SQL между управляемым экземпляром базы данных SQL Azure и SQL Server](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

В этой статье описано, как назначить сервер, на который [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перенаправляет события в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Обратите внимание, что пересылка событий применяется к событиям между серверами, а не к событиям между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , размещенными на одном компьютере. Также заметьте, что для получения перенаправленных событий сервер управления предупреждениями должен быть назначен экземпляром SQL Server по умолчанию.  
  
## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>Перед началом  
  
### <a name="security"></a><a name="Security"></a>безопасность  
  
#### <a name="permissions"></a><a name="Permissions"></a>Permissions  
Необходимо членство в предопределенной роли сервера **sysadmin** .  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>Использование среды SQL Server Management Studio  
  
#### <a name="to-designate-an-events-forwarding-server"></a>Назначение сервера пересылки событий  
  
1.  В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, с которого требуется перенаправлять события на другой сервер.  
  
2.  Щелкните правой кнопкой мыши элемент **Агент SQL Server** и выберите пункт **Свойства**.  
  
3.  В диалоговом окне **Свойства агента SQL Server —** _имя_сервера_ в разделе **Выберите страницу** выберите **Дополнительно**.  
  
4.  В области **Пересылка событий SQL Server**установите флажок **Перенаправить события на другой сервер** .  
  
5.  В списке **Сервер** выберите сервер, а затем на вкладке **События**выполните одно из следующих действий:  
  
    -   Выберите **Необработанные события** , чтобы выполнялась переадресация только событий, не обработанных локальными предупреждениями.  
  
    -   Выберите пункт **Все события** , чтобы выполнялась переадресация всех событий вне зависимости от того, обрабатывались они локальными предупреждениями или нет.  
  
6.  В списке **Если серьезность события равна или превышает** выберите степень серьезности, при которой события переадресуются выбранному серверу.  
  
7.  После завершения нажмите кнопку **ОК**.  
  
