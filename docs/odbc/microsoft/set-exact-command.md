---
title: ЗАДАТЬ точную команду | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SET EXACT command [ODBC]
ms.assetid: 9533d3e0-e7c1-49de-a3a3-0cc4373a91cb
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3e754fff35b6b948ac63d19361067b2d65a07fdd
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300874"
---
# <a name="set-exact-command"></a>Команда SET EXACT
Задает правила сравнения двух строк разной длины.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET EXACT ON | OFF  
```  
  
## <a name="arguments"></a>Аргументы  
 ON  
 Указывает, что выражения должны соответствовать символу, чтобы символ был эквивалентен. Для сравнения все замыкающие пробелы в выражениях игнорируются. Для сравнения более короткие два выражения добавляются справа с пробелами, чтобы соответствовать длине длинного выражения.  
  
 OFF  
 (По умолчанию.) Указывает, что выражение должно соответствовать символу для символа, пока не будет достигнут конец выражения с правой стороны.  
  
## <a name="remarks"></a>Remarks  
 Параметр Задать точную настройку не действует, если обе строки имеют одинаковую длину.  
  
## <a name="string-comparisons"></a>Сравнения строк  
 Visual FoxPro имеет два реляционных оператора, которые проверяют на равенство.  
  
 Оператор = выполняет сравнение двух значений одного типа. Этот оператор подходит для сравнения символов, числовых, дат и логических данных.  
  
 Однако при сравнении символьных выражений с оператором = результаты могут отличаться от предполагаемых. Символьные выражения — это сравниваемый символ слева направо, пока одно из выражений не равно значению другого, пока не будет достигнут конец выражения справа от оператора = (задайте точный параметр) или до тех пор, пока не будут достигнуты концы обоих выражений (задайте точное значение ON).  
  
 Оператор = = можно использовать, если требуется точное сравнение символьных данных. Если два символьных выражения сравниваются с оператором = =, выражения на обеих сторонах оператора = = должны содержать одни и те же символы, включая пробелы, чтобы считаться равными. Параметр Задать точную настройку игнорируется, если символьные строки сравниваются с помощью = =.  
  
 В следующей таблице показано, как выбор оператора и точной настройки влияют на сравнения. (Символ подчеркивания представляет пробел.)  
  
|Сравнение|= ТОЧНАЯ ОТКЛЮЧАЕТСЯ|= ТОЧНОЕ ЗНАЧЕНИЕ ON|= = Точное включение или отключение|  
|----------------|------------------|-----------------|--------------------------|  
|"ABC" = "ABC"|Сопоставление|Сопоставление|Сопоставление|  
|"AB" = "ABC"|Нет совпадения.|Нет совпадения.|Нет совпадения.|  
|"ABC" = "AB"|Сопоставление|Нет совпадения.|Нет совпадения.|  
|"ABC" = "ab_"|Нет совпадения.|Нет совпадения.|Нет совпадения.|  
|"AB" = "ab_"|Нет совпадения.|Сопоставление|Нет совпадения.|  
|"ab_" = "AB"|Сопоставление|Сопоставление|Нет совпадения.|  
|"" = "AB"|Нет совпадения.|Нет совпадения.|Нет совпадения.|  
|"AB" = ""|Сопоставление|Нет совпадения.|Нет совпадения.|  
|"__" = ""|Сопоставление|Сопоставление|Нет совпадения.|  
|"" = "___"|Нет совпадения.|Сопоставление|Нет совпадения.|  
|TRIM ("___") = ""|Сопоставление|Сопоставление|Сопоставление|  
|"" = TRIM ("___")|Сопоставление|Сопоставление|Сопоставление|  
  
## <a name="see-also"></a>См. также:  
 [Команда SET ANSI](../../odbc/microsoft/set-ansi-command.md)
