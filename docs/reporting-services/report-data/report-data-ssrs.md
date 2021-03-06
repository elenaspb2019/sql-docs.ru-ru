---
title: Введение в данные отчета в SQL Server Reporting Services (SSRS)
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-data
ms.topic: conceptual
ms.custom: seodec18
ms.date: 11/18/2019
ms.openlocfilehash: 6317e8161871d7094486ed8b6178847549d8ab96
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "74190724"
---
# <a name="intro-to-report-data-in-sql-server-reporting-services-ssrs"></a>Введение в данные отчета в SQL Server Reporting Services (SSRS)

  Данные отчета могут поступать из нескольких источников данных в организации. Первым шагом при разработке отчета является создание источников и наборов данных, из которых берутся базовые данные отчета. Каждый источник данных содержит сведения о подключении к данным. У каждого набора данных есть команда запроса, определяющая набор полей для использования в качестве данных из источника данных. Для визуализации данных из каждого набора данных, добавьте область данных, например таблицу, матрицу, диаграмму или карту. При обработке отчета в источнике базы данных выполняются запросы и каждая область данных расширяется настолько, насколько требуется для отображения результатов для набора данных.  

> [!NOTE]
> Интеграция служб Reporting Services с SharePoint больше не доступна после выхода SQL Server 2016.

## <a name="data-in-ssrbnoversion"></a>Данные в [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion.md)]  
 ![rs_DataSourcesStory](../../reporting-services/report-data/media/rs-datasourcesstory.gif "rs_DataSourcesStory")  
  
1.  **Источники данных в области данных отчета** . Источник данных появляется в области данных отчета после создания внедренного источника данных или добавления общего источника данных.  
  
2.  **Диалоговое окно соединения** . Используйте диалоговое окно соединения для создания строки соединения или вставки строки соединения.  
  
3.  **Сведения о подключении к данным** . Строка подключения передается модулю обработки данных.  
  
4.  **Учетные данные** . Учетные данные управляются отдельно от строки соединения.  
  
5.  **Модуль обработки данных/поставщик данных** . Соединение с данными может проходить через несколько уровней доступа к данным.  
  
6.  **Внешние источники данных.** Получение данных из реляционных баз данных, многомерных баз данных, списков SharePoint или веб-служб.  


##  <a name="defining-terms"></a><a name="BkMk_ReportDataTerms"></a> Определение терминов  
  
- **Подключение к данным.** Также называется *источником данных*. У подключения к данным есть имя и свойства подключения, зависящие от типа подключения. В соответствии с требованиями безопасности подключение к данным не содержит в себе учетных данных. Подключение к данным не определяет, какие данные будут извлекаться из внешнего источника данных. Для этого при создании набора данных задается запрос.  
  
- **Определение источника данных.** Файл, содержащий XML-представление источника данных отчетов. При публикации отчета его источники данных сохраняются на сервере отчетов или сайте SharePoint в виде определений источников данных независимо от определения отчета. Например, администратор сервера отчетов может обновить строку подключения или учетные данные. Собственный формат сервера отчетов для этого файла — RDS. На сайте SharePoint этот файл сохраняется в формате RSDS.  
  
- **Строка подключения.** Строка подключения — это строковая версия свойств подключения, необходимых для подключения к источнику данных. Свойства подключения различаются в зависимости от типа подключения к данным. Например, см. [Create data connection strings — Report Builder & SSRS](data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md) (Создание строк подключения к данным (построитель отчетов и службы SSRS))  
  
- **Общий источник данных.** Источник данных, доступный на сервере отчетов или на сайте SharePoint, который может использоваться в нескольких отчетах.  
  
- **Внедренный источник данных.** Также называется *источником данных, связанных с отчетом*. Источник данных, определенный в отчете и используемый только этим отчетом.  
  
- **Учетные данные** .   Учетные данные — это сведения для проверки подлинности, которые необходимы для получения доступа к внешним данным.  
  
##  <a name="tips-for-specifying-report-data"></a><a name="BkMk_ReportDataTips"></a> Советы по заданию данных отчета

 Для разработки стратегии данных отчета используйте следующие сведения.  
  
- **Источники данных** Источники данных можно публиковать и управлять ими независимо от отчетов на сервере отчетов или сайте SharePoint. Для каждого источника данных пользователь или владелец базы данных может управлять сведениями о соединении в одном месте. Учетные данные источника данных хранятся в защищенном виде на сервере отчетов; не указывайте пароль в строке подключения. Источник данных можно перенаправить с тестового сервера на рабочий сервер. Можно отключить источник данных, чтобы приостановить все отчеты, которые используют его.  
  
- **Наборы данных.** Наборы данных могут публиковаться и обслуживаться независимо от отчетов или общих источников данных, от которых они зависят. Пользователь или владелец базы данных может обеспечить использование оптимизированных запросов для авторов отчетов. При изменении запроса все отчеты, использующие общий набор данных, используют обновленный запрос. Для повышения производительности набора данных можно включить кэширование. Можно запланировать кэширование запросов на определенное время или использовать общее расписание.  
  
- **Данные, используемые элементами отчета** Элементы отчета могут включать данные, от которых они зависят. Дополнительные сведения об элементах отчета см. в разделе [Элементы отчетов в конструкторе отчетов (службы SSRS)](../../reporting-services/report-design/report-parts-in-report-designer-ssrs.md).  
  
- **Фильтрация данных** Данные отчета могут быть отфильтрованы в запросе или отчете. Для создания каскадных параметров можно использовать наборы данных и переменные запросов. Используя каскадные параметры пользователи могут ограничивать выбор из тысяч вариантов до более управляемого числа. Можно отфильтровать данные в таблице или диаграмме с учетом значений параметров или других указанных пользователем значений.  
  
- **Параметры** Команды запроса набора данных, которые включают в себя переменные запроса, автоматически создают совпадающие параметры отчета. Кроме того, параметры можно создавать вручную. При просмотре отчета на панели инструментов отчета отображаются параметры. Пользователи могут выбрать значения для управления данными отчета или его внешним видом. Чтобы настроить данные отчета для конкретной аудитории, можно создать наборы параметров отчета с различными значениями по умолчанию, которые будут связаны с одним определением отчета. Для настройки данных для различных аудиторий можно также использовать встроенное поле **UserID**. Дополнительные сведения см. в разделах [Параметры отчета (построитель отчетов и конструктор отчетов)](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md) и [Встроенные коллекции в выражениях (построитель отчетов и службы SSRS)](../../reporting-services/report-design/built-in-collections-in-expressions-report-builder.md).  
  
- **Предупреждения данных** После публикации отчета вы можете создавать оповещения на основе данных отчета. Затем при совпадении с указанными правилами вы получите сообщения электронной почты.  
  
- Данные отчета**Сгруппированные и статистически обработанные данные** могут быть сгруппированы и статистически обработаны в запросе или отчете. При статической обработке значений в запросе можно продолжать объединять значения в отчете в пределах ограничений, того, что имеет смысл.  Дополнительные сведения см. в разделах [Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) и [Агрегатная функция (построитель отчетов и службы SSRS)](../../reporting-services/report-design/report-builder-functions-aggregate-function.md).  
  
- Данные отчета**Сортировать данные** могут быть отсортированы в запросе или отчете. В таблицы также можно добавить интерактивную кнопку сортировки, чтобы пользователи могли управлять порядком сортировки.  
  
- **Данные, основанные на выражении** . Так как большинство свойств отчета может быть основано на выражении, а выражения могут включать ссылки на поля наборов данных и параметры отчета, можно писать мощные выражения для управления данными и внешним видом отчета. Можно предоставить пользователю возможность управлять отображаемыми данными с помощью определения параметров.  
  
- **Отобразить данные из набора данных** Как правило, данные из набора данных отображаются в одной или более областях данных, например в таблице и диаграмме.  
  
- **Отобразить данные из нескольких наборов данных**  Можно написать выражения в области данных, основанной на одном наборе данных, которые обнаруживают значения или статистические выражения в других наборах данных. Для отображения данных из других источников в таблицу, основанную на наборе данных, можно включить подотчеты.  
  
 Для определения источника данных для отчета используйте следующий список.  
  
- Решите, какие источника данных и наборы следует использовать: внедренные или общие. Согласуйте с владельцами источников данных технологию проверки подлинности и авторизации, подходящую для вашей организации.  
  
- Ознакомьтесь с используемой в организации архитектурой программного обеспечения уровня данных и потенциальными проблемами, связанными с типами данных. Уясните, как расширения данных и модули обработки данных могут повлиять на результаты запроса. Типы данных отличаются в источнике данных, поставщиках данных и типах данных, которые хранятся в файле определения отчета (RDL-файл).  
  
- Ознакомьтесь с архитектурой и средствами служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] типа «клиент-сервер». Например, в конструкторе отчетов можно создать отчеты на клиентском компьютере, который использует встроенные типы источника данных. При публикации отчета типы источников данных должны поддерживаться на сервере отчетов или сайте SharePoint.  Дополнительные сведения см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](../../reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs.md).  
  
- Источники данных и наборы данных создаются в отчетах и публикуются на сервере отчетов или сайте SharePoint из клиентского средства разработки. Источники данных можно создать непосредственно на сервере отчетов. После того, как они будут опубликованы, учетные данные и другие свойства можно настроить на сервере отчетов. Дополнительные сведения см. в статье [Create data connection strings — Report Builder & SSRS](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md) (Создание строк подключения к данным — построитель отчетов и SSRS) и [Reporting Services Tools](../../reporting-services/tools/reporting-services-tools.md) (Средства Reporting Services).  
  
- Источники данных, которые можно использовать, зависят от установленных модулей обработки данных служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Список поддерживаемых источников данных может различаться в зависимости от используемого клиентского средства разработки, версии и платформы сервера отчетов. Дополнительные сведения см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](../../reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs.md).  
  
- Учетные данные источника данных различаются в зависимости от типа источника данных и способа просмотра отчетов: на клиенте, на сервере отчетов или на сайте SharePoint. Дополнительные сведения см. в разделах [Установка разрешений для элементов сервера отчетов на сайте SharePoint (службы Reporting Services в режиме интеграции с SharePoint)](../../reporting-services/security/set-permissions-for-report-server-items-on-a-sharepoint-site.md), [Задание учетных данных и сведений о соединении для источников данных отчета](../../reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources.md). Сведения об учетных данных для каждого средства см. в разделе [Средства служб Reporting Services](../../reporting-services/tools/reporting-services-tools.md).  
  
## <a name="related-tasks"></a>Связанные задачи

 Задачи, связанные с созданием подключений к данным, добавления данных из внешних источников, наборов данных и запросов.  
  
|||  
|-|-|  
|**Общие задачи**|**Ссылки**|  
|Создание подключений к данным|[Создание строк подключения к данным (построитель отчетов и службы SSRS)](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)|  
|Создание наборов данных и запросов|[Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)|  
|Управление источниками данных после их публикации|[Управление источниками данных отчета](../../reporting-services/report-data/manage-report-data-sources.md)|  
|Управление общими наборами данных после их публикации|[Управление общими наборами данных](../../reporting-services/report-data/manage-shared-datasets.md)|  
|Создание и управление предупреждениями|[Предупреждения об изменении данных в службах Reporting Services](../../reporting-services/reporting-services-data-alerts.md)|  
|Кэширование общих наборов данных|[Общие наборы данных в кэше (службы SSRS)](../../reporting-services/report-server/cache-shared-datasets-ssrs.md)|  
|Планирование общего набора данных для предварительной загрузки кэша|[Расписания](../../reporting-services/subscriptions/schedules.md)|  
|Добавление модуля обработки данных|[Реализация модуля обработки данных](../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)|