---
title: sys. partition_parameters (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- partition_parameters_TSQL
- partition_parameters
- sys.partition_parameters_TSQL
- sys.partition_parameters
dev_langs:
- TSQL
helpviewer_keywords:
- sys.partition_parameters catalog view
ms.assetid: 2012ed9d-3ea3-4c29-9b78-dfa54a392dce
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 012296649dd3a203787692d9e61b4e087983ea39
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87394979"
---
# <a name="syspartition_parameters-transact-sql"></a>sys.partition_parameters (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Содержит строку для каждого параметра функции секционирования.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**function_id**|**int**|Идентификатор функции секционирования, которой принадлежит данный параметр.|  
|**parameter_id**|**int**|Идентификатор параметра. Уникален внутри функции секционирования, начинается с 1.|  
|**system_type_id**|**tinyint**|Идентификатор системного типа параметра. Соответствует столбцу **system_type_id** представления каталога **sys. types** .|  
|**max_length**|**smallint**|Максимальная длина аргумента в байтах.|  
|**precision**|**tinyint**|Для числового аргумента — точность; иначе 0.|  
|**масштаб**|**tinyint**|Масштаб числового аргумента; иначе 0.|  
|**collation_name**|**sysname**|Имя параметров сортировки параметра, если он является символьным; в противном случае значение NULL.|  
|**user_type_id**|**int**|Идентификатор типа данных. Уникален в пределах базы данных. Для системных типов данных **user_type_id**  =  **system_type_id**.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также  
 [Представления каталога функции секционирования &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/partition-function-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sys. partition_functions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-functions-transact-sql.md)   
 [sys.partition_range_values (Transact-SQL)](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)  
  
  
