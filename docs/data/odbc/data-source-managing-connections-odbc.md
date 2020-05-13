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
ms.openlocfilehash: 107a5e20b70f67be74b6e6f861bd539446e9d4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374533"
---
# <a name="data-source-managing-connections-odbc"></a>Источник данных. Управление соединениями (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

В этом разделе рассматриваются следующие вопросы.

- [Как настроить источник данных.](#_core_configuring_a_data_source)

- [Как многопользовательская среда влияет на источник данных и его записи.](#_core_working_in_a_multiuser_environment)

- [Почему обобщается строка соединения с источником данных.](#_core_generalizing_the_connection_string)

- [Как подключиться к источнику данных.](#_core_connecting_to_a_specific_data_source)

- [Как отключиться от источника данных.](#_core_disconnecting_from_a_data_source)

- [Как повторно использовать объект CDatabase](#_core_reusing_a_cdatabase_object).

Подключение к источнику данных означает установление связи с DBMS для доступа к данным. При подключении к источнику данных из приложения через драйвер ODBC водитель делает подключение для вас, либо локально, либо через сеть.

Вы можете подключиться к любому источнику данных, для которого у вас есть драйвер ODBC. Пользователи вашего приложения также должны иметь тот же драйвер ODBC для своего источника данных. Для получения дополнительной информации о [Redistributing ODBC Components to Your Customers](../../data/odbc/redistributing-odbc-components-to-your-customers.md)перераспределении драйверов ODBC см.

## <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a>Настройка источника данных

Администратор ODBC используется для настройки источников данных. Вы также можете использовать администратор ODBC после установки для добавления или удаления источников данных. При создании приложений можно либо направить пользователей к администратору ODBC, чтобы они могли добавлять источники данных, либо построить эту функциональность в приложение, совершая прямые вызовы установки ODBC. Для получения дополнительной информации [см.](../../data/odbc/odbc-administrator.md)

Вы можете использовать файл Excel в качестве источника данных, и вам нужно настроить файл таким образом, чтобы он был зарегистрирован и отображается в диалоговом поле **Select Data Source.**

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Использование файла Excel в качестве источника данных

1. Налажить файл с администратором источника данных ODBC.

1. На вкладке **Файл DSN** нажмите **Добавить**.

1. В поле **для диалога Create New Source** выберите драйвер Excel, а затем нажмите **далее.**

1. Нажмите **«Просмотреть»** и выберите имя файла, используемого в качестве источника даты.

> [!NOTE]
> Для просмотра файлов .xls может потребоваться выбрать **все файлы** в меню выпадающих.

1. Нажмите кнопку **Далее**, а затем кнопку **Готово**.

1. В диалоговом окне **установки ODBC Microsoft Excel** выберите версию базы данных и рабочую книгу.

## <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a>Работа в мультипользовательской среде

Если несколько пользователей подключены к источнику данных, они могут изменять данные во время манипулирования ими в своих рекордных наборах. Аналогичным образом, изменения могут повлиять на записи других пользователей. Для получения дополнительной информации [см. Recordset: Как записи обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) и [транзакций (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a>Обобщение строки соединения

Мастера используют строку соединения по умолчанию для установления соединения с источником данных. Это соединение используется для просмотра таблиц и столбцов во время разработки приложения. Однако эта строка подключения по умолчанию может оказаться неподходящей для подключения пользователей к источнику данных через приложение. Например, их источник данных и путь к его местоположению могут отличаться от того, который используется при разработке приложения. В этом случае следует повторно реализовать функцию [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) в более общем виде и отказаться от реализации мастера. Например, используйте один из следующих подходов:

- Зарегистрируйтесь и управляйте строками соединения с помощью администратора ODBC.

- Отсваивай строку соединения и удалите имя источника данных. Рамки поставляют ODBC в качестве источника данных; во время выполнения ODBC отображает диалоговое окно с просьбой назвать имя источника данных и любую другую необходимую информацию о подключении.

- Предоставь только имя источника данных. ODBC запрашивает идентификатор пользователя и пароль, если это необходимо. Например, перед обобщением строка соединения выглядит следующим образом:

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   Эта строка соединения определяет доверенное соединение, которое использует интегрированную безопасность Windows NT. Следует избегать жесткого кодирования пароля или указания пустого пароля, поскольку это создает серьезную слабость безопасности. Вместо этого можно `GetDefaultConnect` предоставить новую строку соединения, чтобы она запрашивала идентификатор пользователя и пароль.

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

## <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a>Подключение к конкретному источнику данных

Для подключения к определенному источнику данных источник данных уже должен быть настроен с [администратором ODBC.](../../data/odbc/odbc-administrator.md)

#### <a name="to-connect-to-a-specific-data-source"></a>Подключение к определенному источнику данных

1. Постройте `CDatabase` объект.

1. Позвоните `OpenEx` `Open` в его функцию или функцию члена.

Для получения дополнительной информации о том, как указать источник данных, если это что-то другое, чем тот, который вы указали с мастером, [см. CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) или [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) in the *MFC Reference*.

## <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a>Отключение от источника данных

Вы должны закрыть все открытые `Close` записи, прежде чем звонить функции `CDatabase`участника . В записях, `CDatabase` связанных с объектом, который требуется закрыть, любые ожидающие `AddNew` или `Edit` операторы отменяются, а все ожидающие транзакции откатываются.

#### <a name="to-disconnect-from-a-data-source"></a>Отключение от источника данных

1. Вызовите функцию `CDatabase` [замыкать](../../mfc/reference/cdatabase-class.md#close) объект.

1. Уничтожить объект, если вы не хотите, чтобы повторно использовать его.

## <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a>Повторное использование объекта CDatabase

Можно повторно использовать `CDatabase` объект после отключения от него, используете ли он для повторного подключения к тому же источнику данных или для подключения к другому источнику данных.

#### <a name="to-reuse-a-cdatabase-object"></a>Повторное использование объекта CDatabase

1. Закройте исходное соединение объекта.

1. Вместо того, чтобы уничтожить `OpenEx` `Open` объект, позвоните его или функцию члена снова.

## <a name="see-also"></a>См. также раздел

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
