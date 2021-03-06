---
title: MSSQLSERVER_33028 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae11fbccaa4f577815e503d9a0dffaa34c7c04ed
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723607"
---
# <a name="mssqlserver_33028"></a>MSSQLSERVER_33028
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|33028|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|SEC_CRYPTOPROV_CANTOPENSESSION|  
|Текст сообщения|Не удается открыть сеанс для %S_MSG '%.*ls'. Код ошибки поставщика: %d.|  
  
## <a name="explanation"></a>Объяснение  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не смог открыть поставщик служб шифрования, указанный в сообщении об ошибке. Поставщик служб шифрования предоставляет указанный код ошибки. Возможно, придется обратиться к поставщику служб шифрования за дополнительными сведениями об ошибке.  
  
|Код ошибки|Описание|  
|--------------|---------------|  
|0|Успешно. Нет ошибки.|  
|1|Ошибка. Произошла неуказанная или непредвиденная ошибка. Дополнительные сведения об ошибке недоступны.|  
|2|Недостаточно места в буфере. Нельзя выделить пространство для поставщика служб шифрования.|  
|3|Не поддерживается. Этот поставщик служб шифрования не поддерживается данным выпуском. Выберите другой поставщик служб шифрования.|  
|4|Не найден. Указанный поставщик служб шифрования отсутствует, или пользователь не авторизован для доступа к файлам.|  
|5|Ошибка авторизации. Причиной может быть неверный пароль или имя пользователя при создании учетных данных. Может произойти, если учетные данные не существуют.|  
|6|Недопустимый аргумент. Поставщику служб шифрования передан неправильный аргумент.|  
  
## <a name="user-action"></a>Действие пользователя  
Устраните ошибку или обратитесь к поставщику служб шифрования за дополнительными сведениями.  
  
