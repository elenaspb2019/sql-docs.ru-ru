---
title: Операторы (расширения интеллектуального анализа данных) | Документация Майкрософт
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: f274ebc498e5b88b8ae1fbac17c3c972686e348f
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86971618"
---
# <a name="operators-dmx"></a>Операторы (расширения интеллектуального анализа данных)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Операторы расширений интеллектуального анализа данных (DMX) можно использовать для выполнения арифметических операций, сравнения, объединения и логической операции в запросе в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
 В службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] операторы используются для выполнения следующих действий:  
  
-   Поиск значений или объектов, удовлетворяющих заданному условию.  
  
-   Выполнение операции выбора между значениями или выражениями.  
  
 В расширениях интеллектуального анализа данных используется несколько типов операторов, описание которых приводится в последующих разделах. Дополнительные сведения об отдельных операторах см. в разделе [расширения интеллектуального анализа данных &#40;Справочник по операторам DMX&#41;](../dmx/data-mining-extensions-dmx-operator-reference.md).  
  
|Категория оператора.|Тип операции|  
|-----------------------|-----------------------|  
|[Арифметические операторы &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-arithmetic.md)|Выполнение операций сложения, вычитания, умножения и деления.|  
|[Операторы сравнения &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-comparison.md)|Сравнение двух значений или значения с выражением.|  
|[Логические операторы &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-logical.md)|Проверка выполнения условия таких функций как AND, OR или NOT.|  
|[Унарные операторы &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-unary.md)|Выполнение действий над одним операндом.|  
  
 В расширениях интеллектуального анализа данных операторы могут использоваться для составления сложных выражений из более простых. В сложных выражениях операторы выполняются в порядке приоритетов, заданных для них в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Операторы с более высоким приоритетом выполняются раньше операторов с более низким приоритетом. Дополнительные сведения о выражениях см. в разделе [expressions &#40;DMX&#41;](../dmx/expressions-dmx.md).  
  
 При составлении сложного выражения из более простых его тип определяется совокупностью правил для операторов и для приоритетов типов данных. Если результат является символом или значением Юникод, то режим сопоставления результатов определяется службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] путем сочетания правил для операторов с правилами очередности параметров сортировки. Имеются также правила, определяющие точность, масштаб и длину результата на основании данных о точности, масштабе и длине составляющих его простых выражений.  
  
## <a name="see-also"></a>См. также  
 [Расширения интеллектуального анализа данных &#40;Справочник по DMX&#41;](../dmx/data-mining-extensions-dmx-reference.md)   
 [Расширения интеллектуального анализа данных &#40;Справочник по функциям DMX&#41;](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Расширения интеллектуального анализа данных &#40;Справочник по инструкции DMX&#41;](../dmx/data-mining-extensions-dmx-statements.md)   
 [Расширения интеллектуального анализа данных &#40;синтаксические обозначения&#41; DMX](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Расширения интеллектуального анализа данных &#40;синтаксические&#41; DMX-элементы](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Общие прогнозирующие функции &#40;&#41;расширений интеллектуального анализа данных](../dmx/general-prediction-functions-dmx.md)   
 [Структура и использование прогнозирующих запросов расширений интеллектуального анализа данных](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Общие сведения об инструкции расширения интеллектуального анализа данных SELECT](../dmx/understanding-the-dmx-select-statement.md)  
  
  
