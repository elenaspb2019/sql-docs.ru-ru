---
title: MSSQLSERVER_1222 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 34de8d39015b1de1ac220146159a1f5b2d164a52
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85781229"
---
# <a name="mssqlserver_1222"></a>MSSQLSERVER_1222
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|1222|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|LK_TIMEOUT|  
|Текст сообщения|Истекло время ожидания запроса на блокировку.|  
  
## <a name="explanation"></a>Объяснение  
Другая транзакция удерживает блокировку требуемого ресурса дольше, чем данный запрос может ее ожидать.  
  
## <a name="user-action"></a>Действие пользователя  
Для решения проблемы попробуйте выполнить следующие задачи.  
  
1.  Если это возможно, найдите на требуемом ресурсе транзакцию, удерживающую эту блокировку. Используйте динамические административные представления **sys.dm_os_waiting_tasks** и **sys.dm_tran_locks**.  
  
2.  Если транзакция все еще удерживает блокировку, завершите эту транзакцию, если это адекватно.  
  
3.  Выполните запрос еще раз.  

Если данная ошибка возникает часто, измените время ожидания блокировки или вызывающие ошибку транзакции так, чтобы они удерживали блокировку на меньший период времени.  
  
