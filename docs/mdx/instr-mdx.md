---
title: InStr (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 7d7da3f994ed0741ef7ca6bcbe4d6003eea981c7
ms.sourcegitcommit: 99f61724de5edf6640efd99916d464172eb23f92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87363414"
---
# <a name="instr-mdx"></a>Instr (MDX)


  Возвращает положение первого экземпляра строки внутри другой строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InStr([start, ]searched_string, search_string[, compare])  
```  
  
## <a name="arguments"></a>Аргументы  
 *start*  
 Числовое выражение, задающее начальную позицию для каждого поиска (необязательный). Если это значение не указано, поиск начинается с позиции первого символа. Если параметр start имеет значение null, возвращаемое значение функции не определено.  
  
 *searched_string*  
 Строковое выражение, в котором выполняется поиск.  
  
 *search_string*  
 Строковое выражение, которое необходимо найти.  
  
 *Сравнить*  
 Целочисленное значение (не обязательно). Этот аргумент никогда не учитывается. Он определен для совместимости с другими функциями **InStr** на других языках.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение с начальной позицией *строка_замены* в *строка1*.  
  
 Кроме того, функция **InStr** возвращает значения, перечисленные в следующей таблице, в зависимости от условия.  
  
|Условие|Возвращаемое значение|  
|---------------|------------------|  
|String1 имеет нулевую длину|ноль (0)|  
|String1 содержит значение NULL|неопределенный|  
|String2 имеет нулевую длину|запуск|  
|String2 содержит значение NULL|неопределенный|  
|Значение String2 не найдено|ноль (0)|  
|начало больше Len(String2)|ноль (0)|  
  
## <a name="remarks"></a>Remarks  
  
> [!WARNING]  
>  **InStr** всегда выполняет сравнение без учета регистра.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование функции **InStr** и показаны различные сценарии с результатами.  
  
```  
with   
    member [Date].[Date].[Results] as "Results"  
    member measures.[lowercase found in lowercase string] as InStr( "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[uppercase found in lowercase string] as InStr( "abcdefghijklmnñopqrstuvwxyz", "O")  
    member measures.[searched string is empty]            as InStr( "", "o")  
    member measures.[searched string is null]             as iif(IsError(InStr( null, "o")), "Is Error", iif(IsNull(InStr( null, "o")), "Is Null","Is undefined"))  
    member measures.[search string is empty]              as InStr( "abcdefghijklmnñopqrstuvwxyz", "")  
    member measures.[search string is empty start 10]     as InStr(10, "abcdefghijklmnñopqrstuvwxyz", "")  
    member measures.[search string is null]               as iif(IsError(InStr( null, "o")), "Is Error", iif(IsNull(InStr( null, "o")), "Is Null","Is undefined"))  
    member measures.[found from start 10]                 as InStr( 10, "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[NOT found from start 17]             as InStr( 17, "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[NULL start]                          as iif(IsError(InStr( null, "abcdefghijklmnñopqrstuvwxyz", "o")), "Is Error", iif(IsNull(InStr( null, "abcdefghijklmnñopqrstuvwxyz", "o")), "Is Null","Is undefined"))  
    member measures.[start greater than searched length]  as InStr( 170, "abcdefghijklmnñopqrstuvwxyz", "o")  
  
select  [Results] on columns,  
       { measures.[lowercase found in lowercase string]  
       , measures.[uppercase found in lowercase string]  
       , measures.[searched string is empty]  
       , measures.[searched string is null]  
       , measures.[search string is empty]  
       , measures.[search string is empty start 10]  
       , measures.[search string is null]  
       , measures.[found from start 10]  
       , measures.[NOT found from start 17]  
       , measures.[NULL start]   
       , measures.[start greater than searched length]  
       } on rows  
  
from [Adventure Works]  
```  
  
 В следующей таблице показаны полученные результаты.  
  
|Поле в мерах|Результаты|  
|-|-|  
|в строке нижнего регистра найдены символы в нижнем регистре|16|  
|в строке нижнего регистра найдены символы в верхнем регистре|16|  
|искомая строка пуста|0|  
|искомая строка имеет значение NULL|Не задано|  
|строка поиска пуста|1|  
|строка поиска пуста, начало 10|10|  
|искомая строка имеет значение NULL|Не задано|  
|найдено от начало 10|16|  
|НЕ найдено от начало 17|0|  
|Значение NULL в начале|Не задано|  
|начало больше искомой длины|0|  
  
  
