---
title: "Мастер потребителя ATL OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d12020b6adfca2c23dc610b5e596ff883bb9e7ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-ole-db-consumer-wizard"></a>Мастер потребителя ATL OLE DB
Этот мастер устанавливает класс потребителя OLE DB с помощью привязки данных для доступа к указанному источнику данных через указанный поставщик OLE DB.  
  
> [!NOTE]
>  Этот мастер необходимо нажать **источника данных** кнопку, чтобы выбрать источник данных перед вводом имен в `Class` и **h-файл** поля.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Источник данных**  
 **Источника данных** кнопку настраивать указанный источник данных с помощью указанного поставщика OLE DB. При нажатии этой кнопки **свойства связи данных** откроется диалоговое окно. Дополнительные сведения о построении строк соединения и **свойства связи данных** диалоговое окно, в разделе [Обзор API связи данных](https://msdn.microsoft.com/library/ms718102.aspx) в документации пакета SDK для Windows.  
  
> [!NOTE]
>  В предыдущих выпусках, нажав клавиши Shift **источника данных** кнопки открывается диалоговое окно открытия файла позволяет выбрать файл данных (udl). Эта функция больше не поддерживается.  
  
 Диалоговое окно содержит четыре вкладки:  
  
- **Поставщик** вкладка  
  
- **Подключение** вкладка  
  
- **Расширенный** вкладка  
  
- **Все** вкладка  
  
     Следующие дополнительные сведения описаны вкладки **свойства связи данных** диалоговое окно.  
  
     Нажмите кнопку **ОК** завершения. **Выбор объектов базы данных** откроется диалоговое окно. Это диалоговое окно выберите таблицу, представление или хранимая процедура, потребитель будет использовать.  
  
 **Поставщик**  
     Выберите соответствующий поставщик для управления подключением к источнику данных. Тип поставщика, как правило, определяется по типу базы данных, к которому вы подключаетесь. Нажмите кнопку `Next` кнопку или нажмите кнопку **подключения** вкладки.  
  
 **Подключение**  
     Содержимое на этой вкладке зависят от выбранного поставщика. Несмотря на то, что существует множество типов поставщиков, в этом разделе рассматриваются соединения для двух наиболее распространенных: данные SQL и ODBC. Другие типы являются аналогичные вариации в полях, описанных здесь.  
  
     Для данных SQL:  
  
    1. **Выберите или введите имя сервера:** меню раскрывающегося списка для отображения всех зарегистрированных данных серверов в сети, а затем выберите одну.  
  
    2. **Введите данные для входа сервер:** введите имя пользователя и пароль для входа на сервер данных.  
  
    3. **Выберите базу данных на сервере:** щелкните меню раскрывающегося списка для отображения всех зарегистрированных баз данных на сервере данных и выберите один.  
  
         - или -  
  
 **Добавить файл базы данных, как имя базы данных:** указать файл для использования в качестве базы данных, введите явную pathname.  
  
        > [!NOTE]
        >  There is a security problem with the "Allow saving of password" feature of the Data Link Properties dialog box. In "Enter information to log on to the server," there are two radio buttons:  
  
 **Использовать средства безопасности Windows NT**  
  
 **Использовать указанные имя пользователя и пароль**  
  
         If you select **Use a specific user name and password**, you have the option of saving the password (using the check box for "Allow saving password"); however, this option is not secure. It is recommended that you select **Use Windows NT integrated security**; this option is secure because it encrypts the password.  
  
         There might be situations in which you want to select "Allow saving password." For example, if you are releasing a library with a private database solution, you should not access the database directly but instead use a middle-tier application to verify the user (through whatever authentication scheme you choose) and then limit the sort of data available to the user.  
  
         For ODBC data:  
  
         1. **Specify the source of data:** You can use a data source name or a connection string.  
  
 **Используйте имя источника данных:** раскрывающемся списке отображаются источники данных, зарегистрированные на этом компьютере. Можно настроить источники данных в любое время с помощью администратора источников данных ODBC- или -**использовать строку подключения:** либо введите строку соединения, уже получен, или нажмите кнопку **построения** меню; **Выбор источника данных** откроется диалоговое окно. Выберите источник данных файла или компьютера и нажмите кнопку **ОК**.  
  
        > [!NOTE]
        >  You can obtain a connection string by viewing the properties of an existing connection in Server Explorer, or you can create a connection by double-clicking **Add Connection** in Server Explorer.  
  
         2. **Enter information to log on to the server:** Enter a user name and password to log on to the data server.  
  
         3. Enter the initial catalog to use.  
  
         4. Click **Test Connection**; if the test succeeds, click **OK**. If not, check your logon information, try another database, or try another data server.  
  
 **Дополнительно**  
 **Сетевые параметры:** укажите **уровень олицетворения** (уровень олицетворения, который сервер может использовать при олицетворении клиента; соответствует уровни олицетворения RPC) и  **Уровень защиты** (уровень защиты данных, передаваемых между клиентом и сервером; напрямую соответствует уровни защиты RPC).  
  
 **Другое:** в **время ожидания подключения**, укажите количество секунд до истечения периода ожидания бездействия. В **разрешений на доступ к**, укажите разрешения на доступ на подключение к данным.  
  
     Дополнительные сведения о расширенных свойствах инициализации см.  
  
 **Все**  
     На этой вкладке отображается сводка свойств инициализации источника данных и подключение, которое вы указали. Эти значения можно изменить.  
  
     Нажмите кнопку **ОК** завершения. **Выбор объектов базы данных** откроется диалоговое окно. Это диалоговое окно выберите таблицу, представление или хранимая процедура, потребитель будет использовать.  
  
 `Class`  
 После выбора источника данных, это поле заполняется на имя класса по умолчанию на основе таблицы или хранимую процедуру, которая выбрана (см. **выбрать источник данных** ниже). Можно изменить имя класса.  
  
 **h-файл**  
 После выбора источника данных, это поле заполняется именем по умолчанию заголовок класса на основе таблицы или хранимую процедуру, которая выбрана (см. **выбрать источник данных** ниже). Можно изменить имя файла заголовка или выбрать имеющийся файл заголовка.  
  
 **Атрибут**  
 Этот параметр определяет, будет ли мастер создавать классы потребителя с использованием атрибутов или объявлений шаблонов. При выборе этого параметра мастер использует атрибуты вместо объявлений шаблонов (это параметр по умолчанию). Если выбран этот параметр, мастер использует объявления шаблона вместо атрибутов.  
  
-   При выборе потребителя **тип** таблицы, мастер использует `db_source` и **db_table** атрибутов для создания таблицы и метода доступа к таблице объявлений класса, а также использует **db_column**  для создания сопоставление столбцов, например:  
  
 ``` 
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...  
 ```  
  
     Вместо использования `CTable` класса шаблона для объявления в таблице и таблице класса доступа и макросы BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы создать сопоставление столбцов, например:  
  
 ``` 
 // Table accessor class  
    class COrdersAccessor; *// Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
 ```  
  
-   При выборе потребителя **тип** команды, мастер использует `db_source` и **db_command** атрибуты и использует **db_column** для создания сопоставление столбцов, например :  
  
 ```  
 [db_source("<initialization_string>"), db_command("SQL_command")]  
 ... 
 // Column map using db_column is the same as for consumer type of 'table'  
 ```  
  
     Вместо использования команды и объявлений класса метода доступа команды в h-файле класса команды, например:  
  
 ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;  
 ... 
 // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
 // for consumer type of 'table'  
 ```  
  
 В разделе [основные механизмы атрибуты](../../windows/basic-mechanics-of-attributes.md) для получения дополнительной информации.  
  
 **Type**  
 Выберите один из этих переключателей для указания, является ли класс потребителя будет производным от `CTable` или `CCommand` (по умолчанию).  
  
 **Таблица**  
 Выберите этот параметр, если вы хотите использовать `CTable` или **db_table** для создания таблицы и метода доступа к таблице объявления класса.  
  
 **Команда**  
 Выберите этот параметр, если вы хотите использовать `CCommand` или **db_command** для создания команды и доступа к объявления класса. Это параметр выбирается по умолчанию.  
  
 **Поддержка**  
 Установите флажки, чтобы указать типы обновлений для поддержки в объекте-получателе (по умолчанию не используется). Каждый из следующих установит [DBPROP_IRowsetChange](https://msdn.microsoft.com/library/ms715892.aspx) и соответствующие записи для [DBPROP_UPDATABILITY](https://msdn.microsoft.com/library/ms722676.aspx) в наборе свойств карты.  
  
 **Изменение**  
 Указывает, что потребитель поддерживает обновления данных строки в наборе строк.  
  
 **Вставить**  
 Указывает, что потребитель поддерживает вставку строк в наборе строк.  
  
 **Удалить**  
 Указывает, что потребитель поддерживает удаление строк из набора строк.  
  
## <a name="see-also"></a>См. также  
 [Потребителя ATL OLE DB](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Строки соединения и ссылки на данные (OLE DB)](https://msdn.microsoft.com/library/ms718376.aspx)
