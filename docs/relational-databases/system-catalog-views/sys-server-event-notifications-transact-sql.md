---
title: sys. server_event_notifications (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_event_notifications
- sys.server_event_notifications
- sys.server_event_notifications_TSQL
- server_event_notifications_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_event_notifications catalog view
ms.assetid: 1a83a044-3130-4551-95ca-162525846ff5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ee534061f95a9b33ff3febcea758326662599556
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85896475"
---
# <a name="sysserver_event_notifications-transact-sql"></a>sys.server_event_notifications (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает строку для каждого объекта уведомления о событии уровня сервера.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Имя уведомления о событии на сервере. Уникально в пределах всех уведомлений о событиях уровня сервера.|  
|**object_id**|**int**|Идентификационный номер объекта. Уникален в базе данных **master** .|  
|**parent_class**|**tinyint**|Класс родителя. Всегда равен 100 = Сервер.|  
|**parent_class_desc**|**nvarchar(60)**|Описание класса родителя. Всегда SERVER.|  
|**parent_id**|**int**|Всегда равно 0.|  
|**create_date**|**datetime**|Дата создания.|  
|**modify_date**|**datetime**|Дата последнего изменения объекта с помощью инструкции ALTER.|  
|**service_name**|**nvarchar(256)**|Имя целевой службы, куда посылается уведомление.|  
|**broker_instance**|**nvarchar(128)**|Компонент Service Broker, в котором определена именованная целевая служба.|  
|**creator_sid**|**varbinary(85)**|SID имени входа, выполняющего инструкцию, которая создает уведомление о событии. Значение NULL, если в определении уведомления о событии не указано предложение WITH FAN_IN.|  
|**principal_id**|**int**|Идентификатор сервера-участника, который является владельцем данной схемы.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также  
 [Представления каталога объектов &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
