---
title: Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка «Вход»)
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: markingmyname
ms.author: maghan
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
ms.openlocfilehash: 81cca06132cd63bf344d54004895f1bd9a0ab2e7
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "75306746"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a>Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка «Вход»)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  Начиная с версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], в полнотекстовом поиске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется средство запуска управляющей программы полнотекстовой фильтрации SQL (средство запуска FDHOST). Эта служба должна быть запущена при использовании полнотекстового поиска. Сведения о хост-процессах управляющей программы фильтрации см. в разделе «Архитектура компонента Full-Text Search» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 Используйте вкладку **Вход** в диалоговом окне **Свойства запуска управляющей программы полнотекстовой фильтрации (SQL)** , чтобы указать учетную запись, используемую полнотекстовой службой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , изменить пароль учетной записи и запустить или остановить службу. Изменение пароля учетной записи вступает в силу после перезапуска службы.  
  
> [!NOTE]  
>  При изменении имени учетной записи, используемой службой в кластеризованном экземпляре, новая учетная запись должна быть членом группы домена, заданной во время установки службы, или же текущий пользователь должен иметь разрешение на добавление членов в эту группу. Если нет разрешения на изменение состава группы, свяжитесь с администратором домена.  
>   
>  Дополнительные сведения о выборе учетной записи для выполнения службы приводятся в разделе «Настройка учетных записей служб Windows» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="options"></a>Параметры  
 **Встроенная учетная запись**  
 **Локальная система**  
 Укажите учетную запись локальной системы. Для этой учетной записи пароль не нужен. Однако локальная системная учетная запись может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.  
  
 **Локальная служба.**  
 Укажите учетную запись локальной службы. Для этой учетной записи пароль не нужен. Однако учетная запись локальной службы может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.  
  
 **Сетевая служба.**  
 Не рекомендуется использовать учетную запись «Сетевая служба» для служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Для этих служб больше подходят учетные записи «Локальный пользователь» или «Пользователь домена».  
  
 **Эта учетная запись**  
 Укажите локальную или доменную учетную запись, использующую аутентификацию Windows. Для служб рекомендуется использовать доменную учетную запись с минимальными правами.  
  
 **Account Name** (Имя учетной записи)  
 Укажите имя локальной или доменной учетной записи.  
  
 **Пароль**  
 Введите пароль для учетной записи.  
  
 **Подтверждение пароля**  
 Введите пароль для учетной записи еще раз.  
  
 **Начало**  
 Запускает службу.  
  
 **Остановить**  
 Остановить службу.  
  
 **Приостановить**  
 Приостановить службу. Недоступно для этой службы.  
  
 **Возобновить**  
 Возобновить приостановленную работу службы.  
  
  
