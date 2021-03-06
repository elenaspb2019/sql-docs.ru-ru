---
title: Проблемы развития базы данных
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.openlocfilehash: 4fbb7ae6e91f843b84277fc14ab45058a3fa7fac
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86010371"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a>Проблемы развития базы данных (визуальные инструменты для баз данных)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
При изменении структуры развернутой базы данных необходимо следить, чтобы изменения были совместимы с существующими данными и структурой базы данных. Возможно, необходимо будет принять особые меры при выполнении следующих изменений:  
  
-   **Добавление ограничения**. При добавлении ограничения может оказаться, что в базе данных уже содержатся данные, которые не удовлетворяют добавляемому ограничению. При попытке сохранить ограничение [диалоговое окно "Уведомления после сохранения" (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/post-save-notifications-dialog-box-visual-database-tools.md) сообщает, что не удалось создать ограничение в базе данных. Чтобы принудительно принять новое ограничение в базе данных, можно снять флажок **Проверять существующие данные при создании**.  
  
-   **Добавление связи** . При добавлении связи может оказаться, что в базе данных уже содержатся строки таблицы внешнего ключа, для которых отсутствуют соответствующие строки в таблице первичного ключа. То есть существующие данные могут не удовлетворять условию ссылочной целостности. При попытке сохранить новую связь [диалоговое окно "Уведомления после сохранения" (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/post-save-notifications-dialog-box-visual-database-tools.md) сообщает, что серверу базы данных не удалось сохранить исправленную таблицу внешнего ключа. Чтобы принудительно принять изменение, можно снять флажок **Проверять существующие данные при создании**.  
  
-   **Изменение таблицы, входящей в индексированное представление** . При изменении таблицы, входящей в индексированное представление Microsoft SQL Server, индексы представления могут быть потеряны. Дополнительные сведения о повторном создании индексов см. в электронной документации SQL Server.  
  
-   **Удаление объекта** . При удалении объекта, такого как столбец, таблица или представление, из базы данных сначала убедитесь в том, что на него не ссылается другой объект базы данных.  
  
При любых изменениях структуры базы данных необходимо сохранять журнал изменений. Одним из подходов является сохранение скриптов всех изменений, когда-либо сделанных в производственной базе данных.  
  
## <a name="see-also"></a>См. также:  
[Работа с ограничениями](https://msdn.microsoft.com/637098af-2567-48f8-90f4-b41df059833e)  
[Многопользовательские среды (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/multiuser-environments-visual-database-tools.md)  
  
