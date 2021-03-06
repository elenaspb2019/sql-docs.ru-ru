---
title: Тестирование перенесенных объектов базы данных (OracleToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f03ef5e1-66e6-4c84-ada2-252dd5ada82f
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: 858c564c965fe7105c86a3087923887097e4ddac
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "68266482"
---
# <a name="testing-migrated-database-objects-oracletosql"></a>Тестирование объектов баз данных после миграции (OracleToSQL)
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Помощник по миграции для тестера Oracle (SSMA Tester) автоматически проверяет преобразование объектов базы данных и перенос данных, выполняемый SSMA. После завершения миграции SSMA Используйте тестер SSMA, чтобы убедиться, что преобразованные объекты работают одинаково и все данные были переданы должным образом.  
  
С помощью тестера SSMA можно проверить следующие типы объектов:  
  
-   Таблицы  
  
-   Хранимые процедуры, включая Упакованные процедуры.  
  
-   Определяемые пользователем функции, включая упакованные функции.  
  
-   Представления.  
  
-   Автономные инструкции.  
  
Тестер SSMA выполняет объекты, выбранные для тестирования в Oracle, и их аналоги в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. После этого он сравнивает результаты в соответствии со следующими критериями:  
  
-   Совпадают ли изменения в данных таблицы?  
  
-   Совпадают ли значения выходных параметров для процедур и функций?  
  
-   Функции Do возвращают одинаковые результаты?  
  
-   Совпадают ли результирующие наборы?  
  
> [!NOTE]  
> Обратит! Никогда не используйте SSMA Tester в рабочих системах. Во время выполнения тестера изменяются исходная схема и данные. В то же время полное восстановление исходного состояния может оказаться невозможным для некоторых типов протестированного кода.  
  
## <a name="prerequisites"></a>Предварительные требования  
Если вы хотите использовать SSMA Tester, установите пакет расширения SSMA Oracle с включенным параметром **Install Tester Database** .  
  
Чтобы включить Сравнение результирующих данных таблицы, задайте для параметра **создать столбец ROWID** значение **Да** перед началом преобразования схемы. SSMA добавит столбец ROWID во все таблицы во время выполнения команды **Convert Schema** .  
  
Кроме того, проверьте следующее:  
  
-   Клиентские средства Oracle устанавливаются на компьютере, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на котором выполняется.  
  
-   Интеграция со средой CLR включена на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ядро СУБД.  
  
Обратите внимание, что текущая версия тестера SSMA не поддерживает параллельное выполнение разными пользователями на одном исходном или целевом сервере.  
  
## <a name="getting-started"></a>Приступая к работе  
[Создание тестовых случаев &#40;OracleToSQL&#41;](../../ssma/oracle/creating-test-cases-oracletosql.md)  
  
## <a name="see-also"></a>См. также:  
[Установка компонентов SSMA на SQL Server &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md)  
[Параметры проекта &#40;преобразование&#41; &#40;OracleToSQL&#41;](../../ssma/oracle/project-settings-conversion-oracletosql.md)  
  
