---
title: Настройка RDS в Windows 2000 | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS configuration [ADO], Windows 2000
ms.assetid: ef37e858-c05f-4f52-a65f-3ce6037e0d03
author: rothja
ms.author: jroth
ms.openlocfilehash: c5bd4829382a3724b4999e3f87de29a561bd6a29
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82750066"
---
# <a name="configuring-rds-on-windows-2000"></a>Настройка RDS в Windows 2000
Если после обновления до Windows 2000 возникают проблемы при получении правильной работы RDS, выполните следующие действия, чтобы устранить проблему.  
  
1.  Убедитесь, что служба веб-публикаций запущена сначала, перейдя к https://Server с помощью Internet Explorer. Если вы не можете получить доступ к веб-серверу таким образом, откройте командную строку и введите следующую команду: NET START W3SVC.  
  
2.  В меню Пуск выберите команду выполнить. Введите мсдфмап. ini и нажмите кнопку ОК, чтобы открыть файл мсдфмап. ini в блокноте. Проверьте раздел [CONNECT DEFAULT] и, если для параметра доступа задано значение "без доступа", измените его на "только для чтения".  
  
3.  С помощью программы regedit перейдите в раздел "HKEY_LOCAL_MACHINE \Софтваре\микрософт\датафактори\хандлеринфо" и убедитесь, что **хандлеррекуиред** имеет значение 0, а **дефаулсандлер** — "" (строка NULL).  
  
     **Примечание** . При внесении изменений в этот раздел реестра необходимо перезапустить службу веб-публикаций, введя в командной строке следующие команды: "NET ОСТАНАВЛИВАЮТ W3SVC" и "NET START W3SVC".  
  
4.  С помощью программы regedit перейдите в реестре в раздел «HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services\W3SVC\Parameters\ADCLaunch» и убедитесь в наличии ключа с именем **RDSServer.**. Если нет, создайте ее.  
  
5.  С помощью диспетчер служб Интернета выберите веб-сайт по умолчанию и просмотрите свойства виртуального корневого каталога MSADC. Проверьте ограничения по безопасности каталога, IP-адреса и имен доменов. Если установлен флажок "доступ запрещен", выберите значение "предоставлено".  
  
 Не забудьте попытаться перезагрузить сервер, если изменения не появятся, чтобы решить проблему на первый момент.  
  
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](https://go.microsoft.com/fwlink/?LinkId=199565). Начиная с Windows 8 и Windows Server 2012 компоненты RDS Server больше не включены в операционную систему Windows. Перенос приложений, использующих RDS, в [службу данных WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>См. также  
 [Основные принципы RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)


