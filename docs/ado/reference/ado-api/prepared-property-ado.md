---
title: Подготовленное свойство (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Command15::Prepared
helpviewer_keywords:
- Prepared property [ADO]
ms.assetid: 11ca8825-765e-4bb4-a6ce-3f6564ad8755
author: rothja
ms.author: jroth
ms.openlocfilehash: 58cce35e57116618137f4ee776901dba2a44eff4
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761962"
---
# <a name="prepared-property-ado"></a>Свойство Prepared (ADO)
Указывает, следует ли сохранять скомпилированную версию [команды](../../../ado/reference/ado-api/command-object-ado.md) перед выполнением.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **логическое** значение, которое, если задано значение **true**, указывает, что команда должна быть подготовлена.  
  
## <a name="remarks"></a>Remarks  
 Используйте **подготовленное** свойство, чтобы поставщик сохранял подготовленную (или скомпилированную) версию запроса, заданную в свойстве [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) перед первым выполнением объекта [команды](../../../ado/reference/ado-api/command-object-ado.md) . Это может замедлять первое выполнение команды, но после того, как поставщик компилирует команду, поставщик будет использовать скомпилированную версию команды для всех последующих выполнений, что приведет к повышению производительности.  
  
 Если свойство имеет **значение false**, поставщик будет выполнять **Командный** объект напрямую без создания скомпилированной версии.  
  
 Если поставщик не поддерживает подготовку команд, он может вернуть ошибку, если это свойство имеет значение **true**. Если поставщик не возвращает ошибку, он просто игнорирует запрос на подготовку команды и устанавливает для свойства **Prepared** значение **false**.  
  
## <a name="applies-to"></a>Применяется к  
 [Объект Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [Пример подготовленного свойства (Visual Basic)](../../../ado/reference/ado-api/prepared-property-example-vb.md)   
 [Пример свойства Prepared (Visual C++)](../../../ado/reference/ado-api/prepared-property-example-vc.md)   
