---
title: catalog.folders (база данных SSISDB) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: 21a37c16-60aa-4b3f-8bca-ac90ad1697ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6b0a65abc9706af4156767f5ca6bed8fd5a3c69b
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86912530"
---
# <a name="catalogfolders-ssisdb-database"></a>catalog.folders (база данных SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Отображает папки в каталоге служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
|Имя столбца|Тип данных|Description|  
|-----------------|---------------|-----------------|  
|идентификатор|**bigint**|Уникальный идентификатор папки.|  
|name|**sysname(nvarchar(128)**|Имя папки, уникальное в пределах каталога служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].|  
|description|**nvarchar(1024)**|Описание папки.|  
|created_by_sid|**varbinary(85)**|Уникальный идентификатор безопасности пользователя, создавшего папку.|  
|created_by_name|**nvarchar(128)**|Имя пользователя, создавшего папку.|  
|created_time|**datetimeoffset(7)**|Дата и время создания папки.|  
  
## <a name="remarks"></a>Remarks  
 В этом представлении отображается строка для каждой папки в каталоге.  
  
## <a name="permissions"></a>Разрешения  
 Это представление требует применения одного из следующих разрешений:  
  
-   разрешение READ на папку  
  
-   Членство в роли базы данных **ssis_admin**  
  
-   Членство в роли сервера **sysadmin**  
  
> [!NOTE]  
>  Наличие разрешения на выполнение операции на сервере подразумевает наличие разрешения на просмотр сведений об этой операции. Действует защита на уровне строки. Отображаются только строки, на которые у вас имеется разрешение.  
  
  
