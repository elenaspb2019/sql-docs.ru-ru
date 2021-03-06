---
title: Свойства базы данных (страница "Параметры") | Документация Майкрософт
description: Узнайте, как использовать вкладку "Параметры" в диалоговом окне "Свойства базы данных" для просмотра или изменения параметров сортировки базы данных, модели восстановления и других параметров.
ms.custom: ''
ms.date: 08/28/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.options.f1
ms.assetid: a3447987-5507-4630-ac35-58821b72354d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98fcdb49facbc1bae6e7a0b76388c385a0fc05e8
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85630951"
---
# <a name="database-properties-options-page"></a>Свойства базы данных (страница «Параметры»)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Эта страница используется для изменения параметров выделенной базы данных. Дополнительные сведения о параметрах, доступных на этой странице, см. в разделах [Параметры ALTER DATABASE SET (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql-set-options.md) и [ALTER DATABASE SCOPED CONFIGURATION (Transact-SQL)](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md).  
  
## <a name="page-header"></a>Заголовок страницы  
 **Параметры сортировки**  
 Задайте параметры сортировки для базы данных, выбрав из списка. Дополнительные сведения см. в разделе [Set or Change the Database Collation](../../relational-databases/collations/set-or-change-the-database-collation.md).  
  
 **Модель восстановления**  
 Укажите одну из следующих моделей для восстановления базы данных: **Полная**, **С неполным протоколированием** или **Простая**. Дополнительные сведения о моделях восстановления см. в разделе [Модели восстановления (SQL Server)](../../relational-databases/backup-restore/recovery-models-sql-server.md).  
  
 **Уровень совместимости**  
 Укажите последнюю версию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которую поддерживает база данных. Возможные значения см. в статье [Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md). При обновлении базы данных SQL Server уровень совместимости этой базы данных по возможности сохраняется или меняется на минимальный уровень, поддерживаемый новой версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. 
  
 **Тип включения**  
 Указывайте «none» или «partial», чтобы обозначить, что это автономная база данных. Дополнительные сведения об автономных базах данных см. в разделе [Автономные базы данных](../../relational-databases/databases/contained-databases.md). Свойство сервера **Разрешить автономные базы данных** должно иметь значение **TRUE** , прежде чем базу данных можно будет настроить как автономную.  
  
> [!IMPORTANT]  
>  Включение частично автономных баз данных передает управление над доступом к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] владельцам базы данных. Дополнительные сведения см. в разделе [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).  
  
## <a name="automatic"></a>Автоматически  
 **Автоматическое закрытие**  
 Укажите, будет ли база данных закрываться полностью и освобождать ресурсы после выхода последнего пользователя. Допустимые значения — **True** и **False**. Если значение равно **True**, база данных закрывается полностью и освобождает ресурсы после того, как из системы выходит последний пользователь.  

 **Автоматическое создание статистики с добавлением**  
 Укажите, следует ли использовать добавочное создание при создании статистики для каждой секции. Сведения о добавочной статистике см. в разделе [CREATE STATISTICS (Transact-SQL)](../../t-sql/statements/create-statistics-transact-sql.md).  
  
 **Автоматическое создание статистики**  
 Укажите, будет ли база данных автоматически создавать отсутствующие статистические данные оптимизации. Допустимые значения — **True** и **False**. Если значение равно **True**, во время оптимизации автоматически формируются все отсутствующие статистические данные, необходимые запросу для оптимизации. Дополнительные сведения см. в статье [CREATE STATISTICS (Transact-SQL)](../../t-sql/statements/create-statistics-transact-sql.md).  
  
 **Автоматическое сжатие**  
 Укажите, будут ли файлы базы данных доступны для периодического сжатия. Допустимые значения — **True** и **False**. Дополнительные сведения см. в разделе [Shrink a Database](../../relational-databases/databases/shrink-a-database.md).  
  
 **Автоматическое обновление статистики**  
 Укажите, будет ли база данных автоматически обновлять устаревшие статистические данные оптимизации. Допустимые значения — **True** и **False**. Если значение равно **True**, во время оптимизации автоматически формируются все устаревшие статистические данные, необходимые запросу для оптимизации. Дополнительные сведения см. в статье [CREATE STATISTICS (Transact-SQL)](../../t-sql/statements/create-statistics-transact-sql.md).  
  
 **Асинхронное автоматическое обновление статистики**  
 При значении **True** запросы, которые запускают автоматическое обновление устаревшей статистики, не будут ожидать обновления статистики перед компиляцией. Последующие запросы будут использовать обновленную статистику, когда она будет доступна.  
  
 При значении **False**запросы, которые запускают автоматическое обновление устаревшей статистики, будут ожидать, пока обновленная статистика не будет использоваться в плане оптимизации запроса.  
  
 Установка данного параметра в значение **True** имеет смысл только в том случае, если параметр **Автоматическое обновление статистики** также имеет значение **True**.  

## <a name="azure"></a>Azure
При подключении к базе данных SQL Azure в этом разделе содержатся параметры для управления целевым уровнем обслуживания (SLO). По умолчанию как целевой уровень обслуживания для новой базы данных используется "Стандартный S2".

  **Текущий целевой уровень обслуживания**. Определенный целевой уровень обслуживания для использования. Допустимые значения ограничены выбранным выпуском. Если нужное значение целевого уровня обслуживания отсутствует в списке, можно ввести свое значение.

  **Выпуск**. Выпуск базы данных SQL Azure, который следует использовать, например "Базовый" или "Премиум". Если необходимое значение выпуска отсутствует в списке, можно ввести значение, которое должно соответствовать значению, используемому в интерфейсах REST API Azure.
  
  **Максимальный размер**. Указывает максимальный размер базы данных. Если требуемое значение размера отсутствует в списке, можно ввести свое значение. Не указывайте размер для выбора значения по умолчанию для указанного выпуска и целевого уровня обслуживания.
  
## <a name="containment"></a>Containment  
 В автономных базах данных некоторые параметры, обычно настраиваемые на уровне сервера, можно настроить на уровне базы данных.  
  
 **Код языка полнотекстового поиска по умолчанию**  
 Укажите язык, используемый по умолчанию для полнотекстовых индексированных столбцов. Лингвистический анализ полнотекстовых индексированных данных зависит от языка данных. Значением по умолчанию для этого параметра является язык сервера. Дополнительные сведения о языке, соответствующем отображаемой настройке, см. в разделе [sys.fulltext_languages (Transact-SQL)](../../relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql.md).  
  
 **Язык по умолчанию**  
 Язык по умолчанию для всех новых пользователей автономной базы данных, если не указано иное.  
  
 **Включены вложенные триггеры**  
 Разрешает триггерам вызывать срабатывание других триггеров. Вложенность триггеров может достигать максимум 32 уровня. Дополнительные сведения см. в подразделе "Вложенные триггеры" раздела [CREATE TRIGGER (Transact-SQL)](../../t-sql/statements/create-trigger-transact-sql.md).  
  
 **Преобразование пропускаемых слов**  
 Подавляет сообщение об ошибке, если логическая операция по полнотекстовому запросу возвращает нулевые значения из-за пропускаемых слов (стоп-слов). Дополнительные сведения см. в разделе [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).  
  
 **Отсечение двух цифр года**  
 Указывает максимальное значение года, которое можно задать двумя цифрами. Указанный год и предыдущие 99 лет можно задавать двумя цифрами. Все другие года нужно вводить четырьмя цифрами.  
  
 Например, значение по умолчанию 2049 указывает, что дата, введенная в виде «3/14/49», будет интерпретироваться как 14 марта 2049, а дата, введенная в виде «3/14/50» будет интерпретироваться как 14 марта 1950. Дополнительные сведения см. в статье [Настройка параметра конфигурации сервера two digit year cutoff](../../database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option.md).  
  
## <a name="cursor"></a>Курсор  
 **Закрывать курсор при разрешении фиксации**  
 Укажите, будет ли курсор закрываться после фиксации транзакции, открывшей этот курсор. Допустимые значения — **True** и **False**. Если значение равно **True**, закрываются все курсоры, открытые при фиксации или откате транзакции. Если значение равно **False**, при фиксации транзакции такие курсоры остаются открытыми. Если значение равно **False**, откат транзакции закрывает все курсоры, за исключением определенных как INSENSITIVE или STATIC. Дополнительные сведения см. в разделе [SET CURSOR_CLOSE_ON_COMMIT (Transact-SQL)](../../t-sql/statements/set-cursor-close-on-commit-transact-sql.md).  
  
 **Курсор по умолчанию**  
 Задайте поведение курсора по умолчанию. Если значение равно **True**, курсоры по умолчанию объявляются как LOCAL. Если значение равно **False**, курсоры языка [!INCLUDE[tsql](../../includes/tsql-md.md)] по умолчанию объявляются как GLOBAL.  
  
## <a name="database-scoped-configurations"></a>Конфигурации в области базы данных  
 В SQL Server 2016 и базе данных SQL Azure существует ряд свойств конфигурации, которые можно задать на уровне базы данных. Дополнительные сведения о всех этих параметрах см. в разделе [ALTER DATABASE SCOPED CONFIGURATION (Transact-SQL)](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md).  
  
 **Традиционная оценка кратности**  
 Укажите модель оценки кратности оптимизатора запросов для базы данных-источника независимо от уровня совместимости базы данных. Это эквивалентно [флагу трассировки 9481](https://support.microsoft.com/kb/2801413).  
  
 **Традиционная оценка кратности для баз данных-получателей**  
 Укажите модель оценки кратности оптимизатора запросов для баз данных-получателей (при наличии) независимо от уровня совместимости базы данных. Это эквивалентно [флагу трассировки 9481](https://support.microsoft.com/kb/2801413).  
  
 **Максимальное значение DOP**  
 Укажите используемый по умолчанию параметр [MAXDOP](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) для баз данных-источников, который должен использоваться в инструкциях.  
  
 **Максимальное значение DOP для баз данных-получателей**  
 Укажите используемый по умолчанию параметр [MAXDOP](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) для баз данных-получателей (при их наличии), который должен использоваться в инструкциях.  
  
 **Сканирование параметров**  
 Включает или отключает сканирование параметров базы данных-источника. Это эквивалентно [флагу трассировки 4136](https://support.microsoft.com/kb/980653).  
  
 **Сканирование параметров баз данных-получателей**  
 Включает или отключает сканирование параметров баз данных-получателей (при наличии). Это эквивалентно [флагу трассировки 4136](https://support.microsoft.com/kb/980653).  
  
 **Исправления оптимизатора запросов**  
 Включает или отключает исправления оптимизации запросов для базы данных-источника независимо от уровня совместимости базы данных. Это эквивалентно [флагу трассировки 4199](../../t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql.md). Подробности см. в параметре [QUERY_OPTIMIZER_HOTFIXES](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md#qo_hotfixes).  
  
 **Исправления оптимизатора запросов для баз данных-получателей**  
 Включает или отключает исправления оптимизации запросов для баз данных-получателей (при наличии) независимо от уровня совместимости базы данных. Это эквивалентно [флагу трассировки 4199](../../t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql.md). Подробности см. в параметре [QUERY_OPTIMIZER_HOTFIXES](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md#qo_hotfixes).  
  
## <a name="filestream"></a>FILESTREAM  
 **Имя каталога FILESTREAM**  
 Укажите имя каталога для данных FILESTREAM, связанных с выбранной базой данных.  
  
 **Нетранзакционный доступ к файловому потоку**  
 Укажите один из следующих параметров для нетранзакционного доступа через файловую систему к данным FILESTREAM, хранящимся в FileTables: **OFF**, **READ_ONLY** или **FULL**. Если на сервере не включена поддержка FILESTREAM, это значение устанавливается в OFF и отключается. Дополнительные сведения см в разделе [FileTables (SQL Server)](../../relational-databases/blob/filetables-sql-server.md).  
  
## <a name="miscellaneous"></a>Разное  
**Разрешить изоляцию моментального снимка**  
Включает эту функцию.  

 **ANSI NULL по умолчанию**  
 Разрешение значений NULL для всех определяемых пользователем типов данных или столбцов, которые не определены явно как **NOT NULL** в инструкции **CREATE TABLE** или **ALTER TABLE** (состояние по умолчанию). Дополнительные сведения см. в разделах [SET ANSI_NULL_DFLT_ON (Transact-SQL)](../../t-sql/statements/set-ansi-null-dflt-on-transact-sql.md) и [SET ANSI_NULL_DFLT_OFF (Transact-SQL)](../../t-sql/statements/set-ansi-null-dflt-off-transact-sql.md).  
  
 **Включены ANSI NULL**  
 Задание поведения операторов сравнения «равно» (`=`) и «не равно» (`<>`) при использовании со значениями NULL. Допустимые значения: **True** (вкл.) и **False** (выкл.). Если значение равно **True**, всем сравнениям со значениями NULL присваивается значение UNKNOWN. Если значение равно **False**, сравнения значений, отличных от Юникода, со значениями NULL получают значение **True**, если оба они равны NULL. Дополнительные сведения см. в разделе [SET ANSI_NULLS (Transact-SQL)](../../t-sql/statements/set-ansi-nulls-transact-sql.md).  
  
 **Включено заполнение ANSI**  
 Укажите, включено ли заполнение ANSI. Допустимые значения: **True** (вкл.) и **False** (выкл.). Дополнительные сведения см. в разделе [SET ANSI_PADDING (Transact-SQL)](../../t-sql/statements/set-ansi-padding-transact-sql.md).  
  
 **Включены предупреждения ANSI**  
 Укажите поведение по стандарту ISO для некоторых условий возникновения ошибок. Если значение равно **True**, формируется предупреждающее сообщение, если в агрегатных функциях (таких как SUM, AVG, MAX, MIN, STDEV, STDEVP, VAR, VARP или COUNT) появляются значения NULL. Если значение равно **False**, предупреждающее сообщение не выдается. Дополнительные сведения см. в разделе [SET ANSI_WARNINGS (Transact-SQL)](../../t-sql/statements/set-ansi-warnings-transact-sql.md).  
  
 **Включено прерывание при делении на ноль**  
 Укажите, включен ли параметр, разрешающий аварийное прерывание арифметических действий. Допустимые значения — **True** и **False**. Если значение равно **True**, ошибка переполнения или деления на ноль приводит к прерыванию выполнения запроса или пакета. Если произошла ошибка в транзакции, для этой транзакции выполняется откат. Если значение равно **False**, выводится предупреждающее сообщение, но запрос, пакет или транзакция продолжают выполняться, как если бы ошибки не произошло. Дополнительные сведения см. в разделе [SET ARITHABORT (Transact-SQL)](../../t-sql/statements/set-arithabort-transact-sql.md).  
  
 **Объединение со значением NULL дает NULL**  
 Задайте способ объединения значений NULL. Если свойство имеет значение **True**, то **string** + значение NULL возвращает NULL. При значении **False**результатом будет **string**. Дополнительные сведения см. в разделе [SET CONCAT_NULL_YIELDS_NULL (Transact-SQL)](../../t-sql/statements/set-concat-null-yields-null-transact-sql.md).  
  
 **Включены межбазовые цепочки владения**  
 Это значение только для чтения указывает, включен ли параметр межбазовых цепочек владения. Если указано значение **True**, то база данных может быть источником или целевой базой данных в межбазовой цепочке владения. Чтобы установить этот параметр, используйте инструкцию ALTER DATABASE.  
  
 **Включена оптимизация корреляции дат**  
 При значении **True**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ведет статистику корреляции между любыми двумя таблицами в базе данных, которые связаны ограничением FOREIGN KEY и имеют столбцы **datetime** .  
  
 При значении **False**статистика корреляции не ведется.  
 
 **Отложенная устойчивость**  
 Включает эту функцию.  
 
 **Изоляция моментальных снимков Read Committed включена**  
 Включает эту функцию.  
 
 **Автоокругление чисел**  
 Задайте способ обработки ошибок округления базой данных. Допустимые значения — **True** и **False**. Если значение равно **True**, формируется ошибка, когда в выражении происходит потеря точности. Если значение равно **False**, потери точности не приводят к формированию сообщений об ошибках, а результат округляется до степени точности столбца или переменной, в которых сохраняется результат. Дополнительные сведения см. в разделе [SET NUMERIC_ROUNDABORT (Transact-SQL)](../../t-sql/statements/set-numeric-roundabort-transact-sql.md).  
  
 **Определение параметров**  
 Если выбрано значение **SIMPLE**, параметризация запросов выполняется на основе режима базы данных по умолчанию. Если выбрано значение **FORCED**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет параметризацию всех запросов в базе данных.  
  
 **Включены заключенные в кавычки идентификаторы**  
 Укажите, можно ли использовать ключевые слова [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как идентификаторы (имена объектов или переменных), если они заключены в кавычки. Допустимые значения — **True** и **False**. Дополнительные сведения см. в статье [SET QUOTED_IDENTIFIER (Transact-SQL)](../../t-sql/statements/set-quoted-identifier-transact-sql.md).  
  
 **Включены рекурсивные триггеры**  
 Укажите, могут ли триггеры запускаться другими триггерами. Допустимые значения — **True** и **False**. Если значение равно **True**, рекурсивный запуск триггеров разрешен. Если значение равно **False**, запрещается только прямая рекурсия. Чтобы отключить косвенную рекурсию, присвойте параметру сервера вложенные триггеры значение 0, используя процедуру sp_configure. Дополнительные сведения см. в разделе [Создание вложенных триггеров](../../relational-databases/triggers/create-nested-triggers.md).  
  
 **Доверенный**  
 При значении **True**этот параметр только для чтения указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешает доступ к ресурсам вне базы данных в рамках контекста олицетворения, установленного для базы данных. Контекст олицетворения для базы данных можно установить при помощи пользовательской инструкции EXECUTE AS или предложения EXECUTE AS в модулях базы данных.  
  
 Чтобы получить доступ, владелец базы данных также должен иметь разрешение AUTHENTICATE SERVER на уровне сервера.  
  
 Это свойство также разрешает создание и выполнение небезопасных и внешних сборок в базе данных. Владелец базы данных должен задать для этого свойства значение **True**. В дополнение к этому, он должен обладать разрешением EXTERNAL ACCESS ASSEMBLY или UNSAFE ASSEMBLY на уровне сервера.  
  
 По умолчанию для всех пользовательских и системных баз данных (за исключением **MSDB**) это свойство установлено в значение **False**. Оно не изменяется для баз данных **model** и **tempdb** .  
  
 TRUSTWORTHY устанавливается в значение **False** всякий раз, когда база данных присоединяется к серверу.  
  
 Для получения доступа к ресурсам вне базы данных в контексте олицетворения рекомендуется использовать сертификаты и подписи вместе с параметром **Trustworthy** .  
  
 Это свойство задается с помощью инструкции ALTER DATABASE.  
  
 **Включен формат хранения VarDecimal**  
 Этот параметр доступен только для чтения начиная с выпуска [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]. При значении **True**в базе данных включено использование формата хранения vardecimal. Использование формата хранения vardecimal не может быть отключено, пока он используется в каких-либо таблицах базы данных. В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и последующих версиях для всех баз данных включен формат хранения vardecimal. Для этого параметра используется хранимая процедура [sp_db_vardecimal_storage_format](../../relational-databases/system-stored-procedures/sp-db-vardecimal-storage-format-transact-sql.md).  
  
## <a name="recovery"></a>Восстановление  
 **Проверка страниц**  
 Задайте параметр, использующийся для обнаружения незавершенных транзакций ввода-вывода, вызванных ошибками ввода-вывода диска, и уведомления о таких транзакциях. Возможные значения: **None**, **TornPageDetection**и **Checksum**. Дополнительные сведения см. в разделе [Управление таблицей suspect_pages (SQL Server)](../../relational-databases/backup-restore/manage-the-suspect-pages-table-sql-server.md).  
  
 **Целевое время восстановления (в секундах)**  
 Указывает максимальное время, выраженное в секундах, для восстановления определенной базы данных в случае сбоя. Дополнительные сведения см. в разделе [Контрольные точки базы данных (SQL Server)](../../relational-databases/logs/database-checkpoints-sql-server.md).  

## <a name="service-broker"></a>Компонент Service Broker  
**Компонент Broker включен**  
Включает или отключает компонент Service Broker.  

**Учитывать приоритеты компонента Service Broker**  
Свойство компонента Service Broker, доступное только для чтения.  

**Идентификатор компонента Service Broker**  
Идентификатор, доступный только для чтения.  

## <a name="state"></a>Состояние  
 **База данных только для чтения**  
 Укажите, будет ли база данных доступна только для чтения. Допустимые значения — **True** и **False**. Если значение равно **True**, пользователи могут только считывать данные в базе данных. Им не разрешается изменять данные или объекты базы данных. Тем не менее саму базу данных можно удалить, используя инструкцию `DROP DATABASE`. Базу данных нельзя использовать, когда задается новое значение параметра **База данных только для чтения** . Исключением является база данных master, и только системный администратор может использовать базу данных master во время задания параметра.  
  
 **Состояние базы данных**  
 Выводит текущее состояние базы данных. Она не подлежит редактированию. Дополнительные сведения о параметре **Состояние базы данных**см. в разделе [Database States](../../relational-databases/databases/database-states.md).  

 **Шифрование включено**  
 При значении **True**в базе данных включено шифрование. Ключ шифрования базы данных необходим для шифрования. Дополнительные сведения см. в статье [Прозрачное шифрование данных (TDE)](../../relational-databases/security/encryption/transparent-data-encryption.md).  
 
 **Ограничение доступа**  
 Укажите, какие пользователи имеют доступ к базе данных. Возможны следующие значения:  
  
-   **несколько**  
  
     Нормальное состояние производственной базы данных, позволяет нескольким пользователям получать одновременный доступ к базе данных.  
  
-   **Один**  
  
     Используется для операций обслуживания, одновременный доступ к базе данных получает только один пользователь.  
  
-   **Ограниченный**  
  
     Базу данных могут использовать только члены ролей db_owner, dbcreator или sysadmin.  
  


## <a name="see-also"></a>См. также:  
 [ALTER DATABASE (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql.md)   
 [CREATE DATABASE (SQL Server Transact-SQL)](../../t-sql/statements/create-database-sql-server-transact-sql.md)  
  
