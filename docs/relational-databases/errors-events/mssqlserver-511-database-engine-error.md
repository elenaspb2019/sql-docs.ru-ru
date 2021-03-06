---
title: MSSQLSERVER_511 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3e094206a4fbbc9620ff7eed96e01c8b0a06f5f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85715430"
---
# <a name="mssqlserver_511"></a>MSSQLSERVER_511
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|511|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|ROW_TOOBIG|  
|Текст сообщения|Не удалось создать строку размером %d, который превышает допустимый максимум, равный %d.|  
  
## <a name="explanation"></a>Объяснение  
При попытке выполнения операции был превышен максимальный размер строки. Обычно максимальный размер строки составляет 8 060 байт. При использовании некоторых форматов хранения возникают издержки, которые становятся причиной сокращения размера строки, доступного для записи данных. Например, при использовании разреженных столбцов максимальный размер строки составляет 8 018 байт. При выполнении некоторых операций по добавлению или удалению строк, а также некоторых операций, изменяющих тип данных столбца, строка перезаписывается на странице данных, после чего исходная строка удаляется. В процессе выполнения такой операции эффективный размер строки ограничен половиной максимального размера. Причина этого заключается в том, что страница данных должна в течение краткого периода времени содержать обе строки — исходную и измененную.  
  
## <a name="user-action"></a>Действие пользователя  
Если возможно, сократите размер строки.  
  
Если проблема может быть вызвана обновлением строки на месте, необходимо изменять таблицу в несколько этапов. Создайте новую таблицу и передайте в нее данные. Затем удалите исходную таблицу и переименуйте новую таблицу либо выполните усечение исходной таблицы, измените строки в исходной таблице, а затем переместите данные обратно в нее.  
  
