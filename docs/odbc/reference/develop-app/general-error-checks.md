---
title: Общие проверки ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- diagnostic information [ODBC], driver manager error checking
- general error checks [ODBC]
- driver manager [ODBC], error checking
ms.assetid: 0c9a3425-0a7c-48de-9ff6-73601c26283e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 35dc509e0bda51c8d219b76f48b44b2b03dba8cc
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81305565"
---
# <a name="general-error-checks"></a>Проверка общих ошибок
Диспетчер драйверов проверяет одну общую ошибку. Он всегда возвращает SQL_ERROR при возникновении следующей ошибки: функция должна поддерживаться драйвером.
