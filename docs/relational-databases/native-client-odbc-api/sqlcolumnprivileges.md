---
title: SQLColumnPrivileges | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 1d6d66d01c33d6fefdb9637a8c535462ea00a641
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86006653"
---
# <a name="sqlcolumnprivileges"></a>SQLColumnPrivileges
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  **SQLColumnPrivileges** возвращает значение, SQL_SUCCESS, существуют ли значения для параметров*CatalogName*, *SchemaName*, *TableName*или *ColumnName* . Функция**SQLFetch** возвращает значение SQL_NO_DATA, если в этих параметрах заданы недопустимые значения.  
  
 **SQLColumnPrivileges** может выполняться на статическом серверном курсоре. Попытка выполнить **SQLColumnPrivileges** для обновляемого (динамического или ключевого набора ключей) курсора возвратит SQL_SUCCESS_WITH_INFO, указывающее, что тип курсора был изменен.  
  
 Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметре *CatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.  
  
## <a name="see-also"></a>См. также  
 [Функция SQLColumnPrivileges](https://go.microsoft.com/fwlink/?LinkId=59335)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
