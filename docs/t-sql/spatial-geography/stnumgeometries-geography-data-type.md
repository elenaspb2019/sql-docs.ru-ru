---
title: STNumGeometries (тип данных geography) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STNumGeometries (geography Data Type)
- STNumGeometries_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STNumGeometries method
ms.assetid: 6ae7fac2-62f1-420f-9fc9-a09606be9605
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 978a7fd1d6e0f71a4552fdb8b003bb803453ac37
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86554738"
---
# <a name="stnumgeometries-geography-data-type"></a>STNumGeometries (тип данных geography)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает количество **геометрических объектов**, составляющих экземпляр **geography**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STNumGeometries ( )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **int**  
  
 Тип возвращаемых данных CLR: **SqlInt32**  
  
## <a name="remarks"></a>Remarks  
 Этот метод возвращает значение 1, если экземпляр **geography** не является экземпляром **MultiPoint**, **MultiLineString**, **MultiPolygon** или **GeometryCollection**, либо значение 0, если экземпляр **geography** пуст.  
  
## <a name="examples"></a>Примеры  
 В приведенном ниже примере создается экземпляр `MultiPoint` и с помощью метода `STNumGeometries()` определяется количество объектов **geometry**, содержащихся в экземпляре.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('MULTIPOINT((-122.360 47.656), (-122.343 47.656))', 4326);  
SELECT @g.STNumGeometries();  
```  
  
## <a name="see-also"></a>См. также:  
 [Методы OGC в экземплярах Geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
