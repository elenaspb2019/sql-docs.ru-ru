---
title: Метод next (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.next
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 60248447-6908-4036-a779-a501453cd553
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 96d30995c91a7eb038f4aed7bd5dea88d7fe2fcb
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80914710"
---
# <a name="next-method-sqlserverresultset"></a>Метод next (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Перемещает курсор на одну строку вниз от текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public boolean next()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если новая текущая строка является допустимой. Значение **false**, если отсутствуют дополнительные строки для обработки.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Следующий метод указывается с помощью следующего метода в интерфейсе java.sql.ResultSet.  
  
 Курсор результирующего набора сначала располагается перед первой строкой. Первый вызов следующего метода делает первую строку текущей, второй вызов делает вторую строку текущей и т. д.  
  
 Если для текущей строки открыт входной поток, то вызов следующего метода неявно закрывает этот поток. Цепочка предупреждений для объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) очищается, когда считывается новая строка.  
  
## <a name="see-also"></a>См. также:  
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
