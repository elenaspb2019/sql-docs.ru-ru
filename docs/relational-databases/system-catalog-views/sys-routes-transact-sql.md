---
title: sys. Routes (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 09/07/2018
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- routes
- routes_TSQL
- sys.routes
- sys.routes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.routes catalog view
ms.assetid: 8fc65915-8bd6-425b-95d9-6a8468cb1e48
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 831447faa71c3386f394e456f3cbf1243f222083
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85901684"
---
# <a name="sysroutes-transact-sql"></a>sys.routes (Transact-SQL)
[!INCLUDE [SQL Server - ASDBMI](../../includes/applies-to-version/sql-asdbmi.md)]

  Данное представление каталога содержит одну строку для каждого маршрута. Компонент Service Broker использует маршруты для определения сетевого адреса службы.   

|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Имя маршрута, уникальное в пределах базы данных. Не допускает значения NULL.|  
|**route_id**|**int**|Идентификатор маршрута. Не допускает значения NULL.|  
|**principal_id**|**int**|Идентификатор участника базы данных, которому принадлежит маршрут. Допускает значение NULL.|  
|**remote_service_name**|**nvarchar(256)**|Имя удаленной службы. Допускает значение NULL.|  
|**broker_instance**|**nvarchar(128)**|Идентификатор брокера, на котором расположена удаленная служба. Допускает значение NULL.|  
|**контролиру**|**datetime**|Дата и время истечения срока действия маршрута. Обратите внимание, что данное значение не использует местный часовой пояс. Вместо этого значение отображает время истечения срока действия в формате UTC. Допускает значение NULL.|  
|**address**|**nvarchar(256)**|Сетевой адрес, по которому компонент Service Broker отправляет сообщения удаленной службе. Допускает значение NULL. Для Управляемый экземпляр Базы данных SQL адрес должен быть локальным.|  
|**mirror_address**|**nvarchar(256)**|Сетевой адрес участника зеркального отображения для сервера, указанного в адресе. Допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
  
