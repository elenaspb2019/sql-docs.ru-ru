---
title: sys. backup_devices (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- backup_devices_TSQL
- backup_devices
- sys.backup_devices
- sys.backup_devices_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- backup devices [SQL Server], viewing information
- sys.backup_devices catalog view
ms.assetid: 457edaa4-aca1-4bd3-bf8d-734490b80fcd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f9299bdefc1c0c21d7144719139a0fb5fdd9a7d2
ms.sourcegitcommit: dacd9b6f90e6772a778a3235fb69412662572d02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "86279330"
---
# <a name="sysbackup_devices-transact-sql"></a>sys.backup_devices (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждого устройства резервного копирования, зарегистрированного с помощью **sp_addumpdevice** или созданного в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Имя устройства резервного копирования. Уникально в пределах набора.|  
|**type**|**tinyint**|Тип устройства резервного копирования:<br /><br /> 2 = диск;<br /><br /> 3 = дискета (устаревший);<br /><br /> 5 = лента;<br /><br /> 6 = канальное устройство (устаревший);<br /><br /> 7 = виртуальное устройство (для дополнительного использования сторонними поставщиками резервных копий).<br /><br /> 9 = URL-АДРЕС<br /><br />Как правило, используются только диск (2) и URL-адрес (9).|  
|**type_desc**|**nvarchar(60)**|Описание типа устройства резервного копирования:<br /><br /> DISK;<br /><br /> DISKETTE (устаревшее);<br /><br /> TAPE;<br /><br /> PIPE (устаревшее);<br /><br /> VIRTUAL_DEVICE (для дополнительного использования сторонними поставщиками резервных копий).<br /><br /> URL-адрес <br /><br /> Как правило, используются только диск и URL-адрес.|  
|**physical_name**|**nvarchar(260)**|Физическое имя файла или пути в устройстве резервного копирования.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также  
 [Представления каталога &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [BACKUP (Transact-SQL)](../../t-sql/statements/backup-transact-sql.md)   
 [Устройства резервного копирования (SQL Server)](../../relational-databases/backup-restore/backup-devices-sql-server.md)   
 [sp_addumpdevice (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql.md)   
 [Представления каталога баз данных и файлов &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql.md)   
 [Часто задаваемые вопросы о запросах к системному каталогу сервера SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
