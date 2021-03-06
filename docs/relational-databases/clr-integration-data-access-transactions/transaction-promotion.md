---
title: Повышение транзакции | Документация Майкрософт
description: В SQL Server интеграции со средой CLR упрощенная локальная транзакция может повыситься до полностью распространяемой транзакции посредством повышения транзакции.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- distributed transactions [CLR integration]
- promoting transactions [CLR integration]
- Enlist keyword
- transaction promotion [CLR integration]
ms.assetid: 5bc7e26e-28ad-4198-a40d-8b2c648ba304
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267a916e1f3ed9bbcdf3e03240f5fcc39b7eb1b
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85765349"
---
# <a name="transaction-promotion"></a>Повышение транзакции
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  *Повышение* транзакции описывает упрощенную локальную транзакцию, которую можно автоматически повысить до полностью распространяемой транзакции по мере необходимости. Когда управляемая хранимая процедура запускается в рамках транзакции базы данных на сервере, в контексте локальной транзакции запускается код CLR.  Если соединение с удаленным сервером открывается в рамках транзакции базы данных, это соединение с удаленным сервером прикрепляется к распределенной транзакции, а локальная транзакция автоматически повышается до распределенной транзакции. Таким образом повышение транзакции минимизирует избыток распределенных транзакций, откладывая создание распределенной транзакции до тех пор, пока в ней не возникнет необходимость. Повышение транзакции выполняется автоматически, если оно было включено с помощью ключевого слова **прикрепления** и не требует вмешательства разработчика. Поставщик данных .NET Framework для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает поддержку повышения транзакции, обрабатываются классами в пространстве имен .NET Framework **System. Data. SqlClient** .  
  
## <a name="the-enlist-keyword"></a>Ключевое слово Enlist  
 Свойство **ConnectionString** объекта **SqlConnection** поддерживает ключевое слово **прикрепления** , которое указывает, обнаруживает ли **System. Data. SqlClient** транзакционные контексты, и автоматически прикрепляет соединение к распределенной транзакции. Если для этого ключевого слова задано значение true (по умолчанию), соединение автоматически прикрепляется к текущему контексту транзакции открывающего потока. Если для этого ключевого слова задано значение false, то соединение SqlClient не будет взаимодействовать с распределенной транзакцией. Если в строке соединения не указан параметр " **Прикрепление** ", соединение автоматически прикрепляется к распределенной транзакции, если она обнаруживается во время открытия соединения.  
  
## <a name="distributed-transactions"></a>Распределенные транзакции  
 Распределенные транзакции обычно потребляют значительные системные ресурсы. [!INCLUDE[msCoName](../../includes/msconame-md.md)]Координатор распределенных транзакций (MS DTC) управляет такими транзакциями и интегрирует все диспетчеры ресурсов, к которым осуществляется доступ в этих транзакциях. Повышение транзакции, с другой стороны, представляет собой специальную форму транзакции **System. Transactions** , которая фактически делегирует работу простой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] транзакции. **System. Transactions**, **System. Data. SqlClient**и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] координирует работу, связанную с обработкой транзакции, при необходимости повышая ее до полной распределенной транзакции.  
  
 Преимущество использования повышения транзакции заключается в том, что когда соединение открывается с активной транзакцией **TransactionScope** и никакие другие соединения не открываются, транзакция фиксируется в виде упрощенной транзакции, а не наносит дополнительные издержки на полную распределенную транзакцию. Дополнительные сведения о **TransactionScope**см. [в разделе Использование System. Transactions](../../relational-databases/clr-integration-data-access-transactions/using-system-transactions.md).  
  
## <a name="see-also"></a>См. также  
 [Интеграция со средой CLR и транзакции](../../relational-databases/clr-integration-data-access-transactions/clr-integration-and-transactions.md)  
  
  
