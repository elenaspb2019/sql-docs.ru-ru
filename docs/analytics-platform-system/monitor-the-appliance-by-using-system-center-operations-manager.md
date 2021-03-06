---
title: Использование System Center Operations Manager для наблюдения за ТД
description: Используйте System Center Operations Manager (SCOM) для мониторинга устройства аналитики платформы (ТД).
author: mzaman1
ms.prod: sql
ms.technology: data-warehouse
ms.topic: conceptual
ms.date: 04/17/2018
ms.author: murshedz
ms.reviewer: martinle
ms.custom: seo-dt-2019
ms.openlocfilehash: 539c18efe43afcf5436c6913c20cab081974b7f5
ms.sourcegitcommit: 591bbf4c7e4e2092f8abda6a2ffed263cb61c585
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86941126"
---
# <a name="monitor-with-system-center-operations-manager---analytics-platform-system"></a>Мониторинг с помощью системы платформы System Center Operations Manager-Analytics
Используйте System Center Operations Manager (SCOM) для мониторинга устройства аналитики платформы (ТД).
  
## <a name="before-you-begin"></a>Перед началом  
  
### <a name="prerequisites"></a>Обязательные условия  
  
1.  Необходимо установить и запустить System Center Operations Manager 2007 R2, 2012 или 2012 SP1.  
  
2.  Необходимо установить собственный клиент SQL Server 2008 R2 или SQL Server 2012 Native Client.  
  
3.  Пакеты управления для мониторинга SQL Server PDW должны быть установлены, импортированы и настроены. Используйте следующие статьи, чтобы получить инструкции по выполнению этих задач.  
  
    -   [Установка пакетов управления SCOM &#40;Analytics Platform System&#41;](install-the-scom-management-packs.md)  
  
    -   [Импортируйте пакет управления SCOM для PDW &#40;Analytics Platform System&#41;](import-the-scom-management-pack-for-pdw.md) 
    
    -   [Настройка SCOM для мониторинга системы аналитики система &#40;аналитики платформа&#41;](configure-scom-to-monitor-analytics-platform-system.md)
  
<!-- MISSING LINKS    -   [Import the SCOM Management Pack for HDInsight &#40;Analytics Platform System&#41;](import-the-scom-management-pack-for-hdinsight.md)  -->  
   
  
## <a name="to-monitor-sql-server-pdw-with-scom"></a>Мониторинг SQL Server PDW с помощью SCOM  
После настройки пакетов управления SCOM щелкните панель "Мониторинг" SCOM и выполните детализацию до **SQL Server устройства** , а затем **Microsoft SQL Server Parallel Data Warehouse**. Ниже Microsoft SQL Server Parallel Data Warehouse есть четыре варианта: оповещения, устройства, диаграмма устройств и узлы.  
  
### <a name="alerts"></a>Оповещения  
Оповещения — это место, где можно найти текущие оповещения для управления.  
  
![Оповещения](./media/monitor-the-appliance-by-using-system-center-operations-manager/SCOM_SCOM.png "SCOM_SCOM")  
  
### <a name="appliances"></a>Устройства  
Устройства — это место обнаружения и отслеживания SQL Server PDW устройств в вашей среде. Если устройство не отображается здесь и вы создали для него подключение ODBC, то может возникнуть проблема с учетной записью Пдвватчер. Если они отображаются как "не отслеживается", возможно, у вашей учетной записи Пдвмонитор есть какая-то ошибка. Подождите, так как SCOM не вносит изменения в реальном времени, но периодически проверяет наличие новых устройств для отслеживания и периодически отправляет запросы на устройства для мониторинга.  
  
![Устройствами](./media/monitor-the-appliance-by-using-system-center-operations-manager/SCOM_SCOM2.png "SCOM_SCOM2")  
  
### <a name="appliances-diagram"></a>Схема Appliances  
На странице схема Appliances (устройства) можно просмотреть сведения о работоспособности устройства в виде дерева.  
  
![Диаграмма устройств](./media/monitor-the-appliance-by-using-system-center-operations-manager/SCOM_SCOM3.png "SCOM_SCOM3")  
  
### <a name="nodes"></a>Узлы  
Наконец, представление узлы позволяет просматривать работоспособность устройства с помощью каждого узла:  
  
![Узлы](./media/monitor-the-appliance-by-using-system-center-operations-manager/SCOM_SCOM4.png "SCOM_SCOM4")  
  
## <a name="see-also"></a>См. также  
<!-- MISSING LINKS [Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  -->  
[Общие сведения о предупреждениях консоли администрирования &#40;Analytics Platform System&#41;](understanding-admin-console-alerts.md)  
  
