---
title: Управление пакетами с помощью расширения машинного обучения
titleSuffix: Azure Data Studio
description: Сведения о том, как управлять пакетами Python или R в базе данных с помощью расширения машинного обучения для Azure Data Studio.
ms.date: 05/19/2020
ms.reviewer: sstein
ms.prod: azure-data-studio
ms.technology: machine-learning
ms.topic: conceptual
author: dphansen
ms.author: davidph
manager: cgronlun
ms.openlocfilehash: 234c7493852afb4667f9c97b2cb4bb81e119af63
ms.sourcegitcommit: 48d60fe6b6991303a88936fb32322c005dfca2d8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85352401"
---
# <a name="manage-packages-in-database-with-machine-learning-extension-preview-for-azure-data-studio"></a>Управление пакетами в базе данных с помощью расширения машинного обучения (предварительная версия) для Azure Data Studio

Сведения о том, как управлять пакетами Python или R в базе данных с помощью [расширения машинного обучения для Azure Data Studio](machine-learning-extension.md).

> [!IMPORTANT]
> Управление пакетами в базе данных с помощью расширения машинного обучения сейчас поддерживает только [Службы машинного обучения](../machine-learning/sql-server-machine-learning-services.md) в SQL Server 2019.

## <a name="prerequisites"></a>Предварительные требования

- Установите и настройте [расширение машинного обучения для Azure Data Studio](machine-learning-extension.md). Чтобы управление пакетами работало, необходимо указать [путь установки Python или R в параметрах расширения](machine-learning-extension.md#settings).

- Пакет **sqlmlutils**. Если пакет еще не установлен, расширение машинного обучения предложит вам установить его.

- Проверка подлинности Windows не поддерживается для SQL Server на базе Linux. Поэтому для подключения к SQL Server на базе Linux необходимо использовать проверку подлинности SQL.

## <a name="manage-python-packages"></a>Управление пакетами Python

Пакеты Python можно устанавливать и удалять с помощью расширения машинного обучения.

### <a name="install-new-python-package"></a>Установка нового пакета Python

Выполните описанные ниже действия, чтобы установить пакеты Python в базе данных.

1. Щелкните **Управление пакетами в базе данных**.

1. Если вам предложено установить **sqlmlutils**, нажмите кнопку **Да**.

1. На вкладке **Установленные** выберите **Python** в поле **Тип пакета** и выберите свою базу данных в поле **Расположение**.

1. Перейдите на вкладку **Добавить новый**.

1. Укажите пакет Python, который хотите установить, в поле **Search Python packages** (Поиск пакетов Python), а затем нажмите кнопку **Поиск**.

1. Убедитесь, что пакет указан в поле **Имя пакета**, а требуемая версия указана в поле **Версия пакета**.

1. Щелкните **Install**(Установить).

1. Нажмите кнопку **Закрыть** и убедитесь, что пакет был успешно установлен в разделе **Задачи**.

### <a name="uninstall-a-python-package"></a>Удаление пакета Python

Выполните описанные ниже действия, чтобы удалить пакеты Python в базе данных.

> [!NOTE]
> Удалить можно только пакеты, установленные в вашей базе данных. Невозможно удалить пакет, который был предварительно установлен вместе со Службами машинного обучения SQL Server.

1. Щелкните **Управление пакетами в базе данных**.

1. Если вам предложено установить **sqlmlutils**, нажмите кнопку **Да**.

1. На вкладке **Установленные** выберите **Python** в поле **Тип пакета** и выберите свою базу данных в поле **Расположение**.

1. Выберите пакеты, которые вы хотите удалить.

1. Щелкните **Удалить выбранные пакеты**.

1. Нажмите кнопку **Закрыть** и убедитесь, что пакет был успешно установлен в разделе **Задачи**.

## <a name="manage-r-packages"></a>Управление пакетами R

Пакеты R можно устанавливать и удалять с помощью расширения машинного обучения.

### <a name="install-new-r-package"></a>Установка нового пакета R

Выполните описанные ниже действия, чтобы установить пакеты Python в базе данных.

1. Щелкните **Управление пакетами в базе данных**.

1. Если вам предложено установить **sqlmlutils**, нажмите кнопку **Да**.

1. На вкладке **Установленные** выберите **R** в поле **Тип пакета** и выберите свою базу данных в поле **Расположение**.

1. Перейдите на вкладку **Добавить новый**.

1. Укажите пакет R, который хотите установить, в поле **Search R packages** (Поиск пакетов R), а затем нажмите кнопку **Поиск**.

1. Убедитесь, что пакет указан в поле **Имя пакета**, а требуемая версия указана в поле **Версия пакета**.

1. Щелкните **Install**(Установить).

1. Нажмите кнопку **Закрыть** и убедитесь, что пакет был успешно установлен в разделе **Задачи**.

### <a name="uninstall-an-r-package"></a>Удаление пакета R

Выполните описанные ниже действия, чтобы удалить пакеты R в базе данных.

> [!NOTE]
> Удалить можно только пакеты, установленные в вашей базе данных. Невозможно удалить пакет, который был предварительно установлен вместе со Службами машинного обучения SQL Server.

1. Щелкните **Управление пакетами в базе данных**.

1. Если вам предложено установить **sqlmlutils**, нажмите кнопку **Да**.

1. На вкладке **Установленные** выберите **R** в поле **Тип пакета** и выберите свою базу данных в поле **Расположение**.

1. Выберите пакеты, которые вы хотите удалить.

1. Щелкните **Удалить выбранные пакеты**.

1. Нажмите кнопку **Закрыть** и убедитесь, что пакет был успешно установлен в разделе **Задачи**.

## <a name="next-steps"></a>Дальнейшие действия

- [Расширение "Машинное обучение" для Azure Data Studio](machine-learning-extension.md)
- [Составление прогнозов](machine-learning-extension-predictions.md)
- [Импорт или просмотр моделей](machine-learning-extension-import-view-models.md)
- [Записные книжки в Azure Data Studio](notebooks-guidance.md)
- [Документация по машинному обучению на SQL](../machine-learning/index.yml)
