---
title: Создание пользовательского псевдонима для типа данных | Документация Майкрософт
description: Узнайте, как на SQL Server 2019 создать пользовательский псевдоним типа данных с помощью SQL Server Management Studio или Transact-SQL.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.userdefineddatatype.general.f1
- sql13.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 7e2bc61b8c69f3e52fc5149a1c3313ee4f0dc8d1
ms.sourcegitcommit: 99f61724de5edf6640efd99916d464172eb23f92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87363165"
---
# <a name="create-a-user-defined-data-type-alias"></a>Создание псевдонима определяемого пользователем типа данных
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  В этом разделе описывается создание нового определяемого пользователем псевдонима типа данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **В этом разделе**  
  
-   **Перед началом работы**  
  
     [Ограничения](#Restrictions)  
  
     [Безопасность](#Security)  
  
-   **Создание пользовательского псевдонима типа данных с помощью различных средств.**  
  
     [Среда SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Ограничения  
  
-   Определяемый пользователем псевдоним типа данных должен соответствовать правилам для идентификаторов.  
  
###  <a name="security"></a><a name="Security"></a> безопасность  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 Требует разрешения CREATE TYPE в текущей базе данных и разрешения ALTER для схемы *schema_name*. Если аргумент *schema_name* не указан, в действие вступают принимаемые по умолчанию правила разрешения имен с целью определения схемы для текущего пользователя.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
  
#### <a name="to-create-a-user-defined-data-type"></a>Создание пользовательского типа данных  
  
1.  Раскройте в обозревателе объектов по очереди узел **Базы данных**, узел конкретной базы данных, узел **Программирование**и **Типы**, щелкните правой кнопкой мыши узел **Определяемые пользователем типы данных**и выберите пункт **Создать определяемый пользователем тип данных**.  
  
     **Разрешить значения NULL**  
     Указание, допускает ли определяемый пользователем тип данных значения NULL. Допустимость значений NULL для существующего определенного пользователем типа данных не может быть изменена.  
  
     **Data type**  
     Выберите базовый тип данных из списка. В списке показаны все типы данных, за исключением типов **geography**, **geometry**, **hierarchyid**, **sysname**, **timestamp** и **xml** . Тип данных существующего определенного пользователем типа данных не может быть изменен.  
  
     **Default**  
     При необходимости выберите значение по умолчанию, которое будет привязано к псевдониму пользовательского типа данных.  
  
     **Длина/точность**  
     Отображает длину и точность представления типа данных, где это применимо. Параметр**Длина** применяется к символьным определяемым пользователем типам данных; параметр **Точность** ― только к числовым определяемым пользователем типам данных. Метка изменяется в зависимости от типа данных, выбранного ранее. Это поле не редактируется, если длина или точность выбранного элемента данных фиксированы.  
  
     Длина не отображается для типов данных **nvarchar(max)** , **varchar(max)** и **varbinary(max)** .  
  
     **имя**;  
     При создании нового псевдонима определяемого пользователем типа данных введите уникальное имя, которое будет использоваться в базе данных для представления этого псевдонима определяемого пользователем типа данных. Максимальное количество символов должно соответствовать системному типу данных **SYSNAME** . Имя существующего псевдонима определяемого пользователем типа данных не может быть изменено.  
  
     **Правило**  
     При желании выберите правило для привязки к псевдониму определяемого пользователем типа данных.  
  
     **Масштабирование**  
     Определяет максимальное количество десятичных разрядов, которые могут быть сохранены справа от десятичного разделителя.  
  
     **Схема**  
     Выберите схему из списка всех схем, доступных данному пользователю. Выбором по умолчанию является схема по умолчанию для текущего пользователя.  
  
     **Память**  
     Отображает максимальный размер для псевдонима определяемого пользователем типа данных. Максимальные размеры хранилища могут быть разными и определяются точностью.  
  
    |Точность|Максимальный размер хранилища|  
    |-|-|  
    |1–9|5|  
    |10–19|9|  
    |20–28|13|  
    |29–38|17|  
  
     Для типов данных **nchar** и **nvarchar** значение размера хранилища всегда в два раза больше значения параметра **Длина**.  
  
     Значение хранилища не отображается для типов данных **nvarchar(max)** , **varchar(max)** и **varbinary(max)** .  
  
2.  В диалоговом окне **Создание определяемого пользователем типа данных** введите в поле **Схема** схему, которая будет владеть новым псевдонимом типа данных, или выберите схему, нажав кнопку обзора.  
  
3.  В поле **Имя** введите имя нового псевдонима типа данных.  
  
4.  В поле **Тип данных** выберите тип, на основе которого будет создан новый псевдоним типа данных.  
  
5.  Заполните поля **Длина**, **Точность**и **Масштаб** , если это требуется для создаваемого типа данных.  
  
6.  Если новый псевдоним типа данных должен поддерживать значения NULL, установите флажок **Разрешить значения NULL** .  
  
7.  Если требуется связать с новым псевдонимом типа данных значение по умолчанию или правило, заполните в области **Привязка** поле **По умолчанию** или **Правило** . В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нельзя создавать правила или значения по умолчанию. Используйте [!INCLUDE[tsql](../../includes/tsql-md.md)]. Примеры кода, создающего умолчания и правила, доступны в окне обозревателя шаблонов.  

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Использование Transact-SQL  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a>Создание псевдонима определяемого пользователем типа данных  
  
1.  Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  На панели «Стандартная» нажмите **Создать запрос**.  
  
3.  Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**. В следующем примере создается псевдоним типа данных на базе определенного в системе типа данных `varchar` . Псевдоним типа данных `ssn` используется для столбцов, хранящих номера карточек социального страхования, состоящих из 11 разрядов (999-99-9999). Эти столбцы не могут иметь значение NULL.  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a>См. также:  
 [Идентификаторы баз данных](../../relational-databases/databases/database-identifiers.md)   
 [CREATE TYPE (Transact-SQL)](../../t-sql/statements/create-type-transact-sql.md)  
  
  
