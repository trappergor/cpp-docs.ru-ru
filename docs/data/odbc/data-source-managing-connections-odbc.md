---
title: Источник данных. Управление соединениями (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
ms.openlocfilehash: 6186199ea51c1fc966783ed3c0a73496c6a307ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213301"
---
# <a name="data-source-managing-connections-odbc"></a>Источник данных. Управление соединениями (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

В этом разделе рассматриваются следующие вопросы.

- [Настройка источника данных](#_core_configuring_a_data_source).

- [Влияние многопользовательской среды на источник данных и его наборы записей](#_core_working_in_a_multiuser_environment).

- [Зачем нужно обобщить строку подключения к источнику данных](#_core_generalizing_the_connection_string).

- [Подключение к источнику данных](#_core_connecting_to_a_specific_data_source).

- [Отключение от источника данных](#_core_disconnecting_from_a_data_source).

- [Повторное использование объекта CDatabase](#_core_reusing_a_cdatabase_object).

Подключение к источнику данных означает установку связи с СУБД для доступа к данным. При подключении к источнику данных из приложения с помощью драйвера ODBC драйвер устанавливает подключение локально или по сети.

Можно подключиться к любому источнику данных, для которого имеется драйвер ODBC. У пользователей приложения также должен быть один и тот же драйвер ODBC для источника данных. Дополнительные сведения о распространении драйверов ODBC см. [в статье распространение компонентов ODBC для клиентов](../../data/odbc/redistributing-odbc-components-to-your-customers.md).

##  <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a>Настройка источника данных

Для настройки источников данных используется администратор ODBC. Вы также можете использовать администратор ODBC после установки, чтобы добавить или удалить источники данных. При создании приложений можно либо направить пользователей к администратору ODBC, чтобы они могли добавить источники данных, либо создать эту функцию в приложении, установив прямые вызовы ODBC. Дополнительные сведения см. в разделе [Администратор ODBC](../../data/odbc/odbc-administrator.md).

Вы можете использовать файл Excel в качестве источника данных, и необходимо настроить его так, чтобы он был зарегистрирован и появился в диалоговом окне **Выбор источника данных** .

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Использование файла Excel в качестве источника данных

1. Настройте файл с помощью администратора источников данных ODBC.

1. На вкладке **Файловый DSN** нажмите кнопку **Добавить**.

1. В диалоговом окне **Создание нового источника данных** выберите драйвер Excel и нажмите кнопку **Далее**.

1. Нажмите кнопку **Обзор**и выберите имя файла, который будет использоваться в качестве источника даты.

> [!NOTE]
>  Чтобы просмотреть XLS-файлы, может потребоваться выбрать **все файлы** в раскрывающемся меню.

1. Щелкните **Далее**и затем нажмите кнопку **Готово**.

1. В диалоговом окне **Установка ODBC Microsoft Excel** выберите версию базы данных и книгу.

##  <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a>Работа в многопользовательской среде

Если к источнику данных подключено несколько пользователей, они могут изменять данные при работе с ними в наборах записей. Аналогичным образом изменения могут повлиять на наборы записей других пользователей. Дополнительные сведения см. в разделе [набор записей: как наборы записей обновляют записи (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) и [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a>Обобщение строки подключения

Для установления соединения с источником данных мастеры используют строку подключения по умолчанию. Это подключение используется для просмотра таблиц и столбцов при разработке приложения. Однако эта строка подключения по умолчанию может не подойти для подключений пользователей к источнику данных через приложение. Например, источник данных и путь к его расположению могут отличаться от тех, которые используются при разработке приложения. В этом случае следует повторно реализовать функцию-член [CRecordset:: жетдефаултконнект](../../mfc/reference/crecordset-class.md#getdefaultconnect) более универсальным образом и отменить реализацию мастера. Например, используйте один из следующих подходов:

- Регистрация строк подключения и управление ими с помощью администратора ODBC.

- Измените строку подключения и удалите имя источника данных. Платформа предоставляет ODBC в качестве источника данных; во время выполнения ODBC отображает диалоговое окно с запросом имени источника данных и других необходимых сведений о соединении.

- Укажите только имя источника данных. При необходимости ODBC запрашивает идентификатор пользователя и пароль. Например, перед обобщением строка подключения выглядит следующим образом:

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   Эта строка подключения указывает доверительное соединение, использующее встроенную безопасность Windows NT. Следует избегать жесткого кодирования пароля или указания пустого пароля, так как это создает серьезную слабую уязвимость системы безопасности. Вместо этого можно присвоить `GetDefaultConnect` новой строке подключения, чтобы она запрашивает идентификатор пользователя и пароль.

    ```cpp
    // User must select data source and supply user ID and password:
        return "ODBC;";
    // User ID and password required:
        return "ODBC;DSN=mydb;";
    // Password required (myuserid must be replaced with a valid user ID):
        return "ODBC;DSN=mydb;UID=myuserid;";
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";
    ```

##  <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a>Подключение к определенному источнику данных

Чтобы подключиться к определенному источнику данных, в источнике данных уже должен быть настроен [Администратор ODBC](../../data/odbc/odbc-administrator.md).

#### <a name="to-connect-to-a-specific-data-source"></a>Подключение к определенному источнику данных

1. Создайте объект `CDatabase`.

1. Вызовите его `OpenEx` или `Open` функцию члена.

Дополнительные сведения о том, как указать источник данных, если он отличается от указанного в мастере, см. в разделе [CDatabase:: опенекс](../../mfc/reference/cdatabase-class.md#openex) или [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) в *справочнике по MFC*.

##  <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a>Отключение от источника данных

Прежде чем вызывать функцию члена `Close` `CDatabase`, необходимо закрыть все открытые наборы записей. В наборе записей, связанном с объектом `CDatabase`, который необходимо закрыть, все отложенные `AddNew` или операторы `Edit` отменяются и выполняется откат всех ожидающих транзакций.

#### <a name="to-disconnect-from-a-data-source"></a>Отключение от источника данных

1. Вызовите функцию [закрытия](../../mfc/reference/cdatabase-class.md#close) элемента `CDatabase` объекта.

1. Удалите объект, если вы не хотите его использовать повторно.

##  <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a>Повторное использование объекта CDatabase

Можно повторно использовать объект `CDatabase` после отключения от него, использовать его для повторного подключения к тому же источнику данных или для подключения к другому источнику данных.

#### <a name="to-reuse-a-cdatabase-object"></a>Повторное использование объекта CDatabase

1. Закройте исходное соединение объекта.

1. Вместо уничтожения объекта вызовите его `OpenEx` или `Open` функцию члена.

## <a name="see-also"></a>См. также раздел

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
