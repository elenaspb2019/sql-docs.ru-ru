---
title: Соединение с SQL Server для удаления | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 030b10c2-6b88-4c2c-bf67-22994be25a60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c2db76002be78fba04d324036b3eb5af1b81585a
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916290"
---
# <a name="connection-to-sql-server-for-delete"></a>Соединение с SQL Server для удаления

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Если имя входа, не имеющее роли с разрешением на запись в базе данных MSXDBCDC (например, **db_owner** ), пытается удалить экземпляр Oracle CDC, открывается диалоговое окно "Подключение к SQL Server".  
  
 Чтобы удалить экземпляр Oracle CDC, нужно ввести в это окно учетные данные имени входа, имеющего разрешение на запись в базу данных MSXDBCDC, например учетные данные члена роли базы данных **db_owner** .  
  
 В диалоговом окне «Подключение к SQL Server» введите следующие данные.  
  
 **Имя сервера**  
 Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Аутентификация**  
 Выберите один из следующих вариантов:  
  
-   **Проверка подлинности Windows.**  
  
-   **Проверка подлинности SQL Server**. При выборе этого варианта необходимо ввести **Имя** и **Пароль** для пользователя в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с которым устанавливается соединение.  
  
 **Параметры**  
 Чтобы просмотреть доступные для настройки параметры, щелкните стрелку. Для них можно оставить значения по умолчанию. Доступные параметры:  
  
-   **Время ожидания подключения**: введите время (в секундах), в течение которого программа ожидает подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , прежде чем выдать ошибку времени ожидания. Значение по умолчанию ― **15**.  
  
-   **Время ожидания выполнения**: введите время (в секундах), в течение которого программа ожидает выполнения команды SQL, прежде чем выдать ошибку времени ожидания. Значение по умолчанию — **30**.  
  
-   **Шифрование подключения**: выберите **Шифрование подключения** , чтобы устанавливаемое подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шифровалось для обеспечения конфиденциальности.  
  
-   **Дополнительно**: нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".  
  
## <a name="see-also"></a>См. также:  
 [Разрешения, необходимые службе CDC для соединения с SQL Server](../../integration-services/change-data-capture/sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
