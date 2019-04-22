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
ms.openlocfilehash: 5b646ca0eb86d3addabaad59ca23f56cfe914114
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041168"
---
# <a name="data-source-managing-connections-odbc"></a>Источник данных. Управление соединениями (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Содержание раздела:

- [Настройка источника данных](#_core_configuring_a_data_source).

- [Воздействие многопользовательской среды на источник данных и его наборы записей](#_core_working_in_a_multiuser_environment).

- [Необходимость в создании строки подключения к источнику данных](#_core_generalizing_the_connection_string).

- [Как подключиться к источнику данных](#_core_connecting_to_a_specific_data_source).

- [Отключение от источника данных](#_core_disconnecting_from_a_data_source).

- [Как повторное использование объекта CDatabase](#_core_reusing_a_cdatabase_object).

Подключение к источнику данных предполагает установление соединения с СУБД для доступа к данным. При подключении к источнику данных из приложения с помощью драйвера ODBC драйвер производит подключение, локально или по сети.

Можно подключиться к любому источнику данных, для которого у вас есть драйвер ODBC. Пользователи приложения также должны иметь один и тот же драйвер ODBC для источника данных. Дополнительные сведения о распространении драйверов ODBC, см. в разделе [распространение компонентов ODBC среди клиентов](../../data/odbc/redistributing-odbc-components-to-your-customers.md).

##  <a name="_core_configuring_a_data_source"></a> Настройка источника данных

Администратор ODBC используется для настройки источников данных. Можно также использовать администратор ODBC после установки для добавления или удаления источников данных. При создании приложений, либо можно направлять пользователей для администратора ODBC добавлять источники данных, или можно реализовать эту функциональность в приложения, выполнение прямых вызовов установки ODBC. Дополнительные сведения см. в разделе [администратор ODBC](../../data/odbc/odbc-administrator.md).

Файл Excel можно использовать как источник данных, и вам нужно настроить файл таким образом, чтобы он был зарегистрирован и отображался в **Выбор источника данных** диалоговое окно.

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Чтобы использовать файл Excel в качестве источника данных

1. Настройте файл с помощью администратора источников данных ODBC.

1. На **файловый DSN** щелкните **добавить**.

1. В **Создание нового источника данных** диалоговом окне выберите драйвер Excel, а затем нажмите кнопку **Далее**.

1. Нажмите кнопку **Обзор**и выберите имя файла для использования в качестве источника данных.

> [!NOTE]
>  Может потребоваться выбрать **все файлы** в раскрывающемся меню, чтобы отобразить XLS-файлы.

1. Щелкните **Далее**и затем нажмите кнопку **Готово**.

1. В **Настройка ODBC Microsoft Excel** диалогового окна выберите версию базы данных и книги.

##  <a name="_core_working_in_a_multiuser_environment"></a> Работа в многопользовательской среде

Если несколько пользователей подключены к источнику данных, они могут изменять данные, хотя при работе с ней в наборах записей. Аналогичным образом могут влиять на наборы записей других пользователей. Дополнительные сведения см. в разделе [набор записей: Принципы обновления записей в наборе записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) и [транзакция (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="_core_generalizing_the_connection_string"></a> Создание обобщенной строки подключения

Мастера используйте строку подключения по умолчанию для установления соединения с источником данных. Подключение можно использовать для просмотра таблиц и столбцов, при разработке приложения. Тем не менее эта строка подключения по умолчанию может оказаться непригодной для пользовательских подключений к источнику данных посредством приложения. Например источник данных и путь к нему может отличаться от той, используемых при разработке приложения. В этом случае следует повторно реализовать [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) член работать в более универсальный код и удалить реализацию мастера. Например используйте один из следующих подходов:

- Регистрация и управление строками подключения, с помощью администратора ODBC.

- Измените строку подключения и удалите имя источника данных. Среда .NET framework предоставляет ODBC в качестве источника данных. во время выполнения ODBC выводит диалоговое окно с запросом для имени, а также любые другие необходимые для подключения к источнику данных.

- Укажите только имя источника данных. ODBC запрашивает идентификатор пользователя и пароль, если это необходимо. Например перед приведением к обобщенному виду строка подключения выглядит следующим образом:

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   Эта строка подключения указывает доверительное соединение, который использует Windows встроенная система безопасности NT. Следует избегать жесткого кодирования паролей или указания пустого пароля, так как это создает уязвимости безопасности. Вместо этого можно предоставить `GetDefaultConnect` новую строку подключения, чтобы он запрашивает идентификатор пользователя и пароль.

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

##  <a name="_core_connecting_to_a_specific_data_source"></a> Подключение к определенному источнику данных

Чтобы подключиться к определенному источнику данных, источник данных должен быть заранее настроен с [администратор ODBC](../../data/odbc/odbc-administrator.md).

#### <a name="to-connect-to-a-specific-data-source"></a>Для подключения к определенному источнику данных

1. Создать `CDatabase` объекта.

1. Вызовите его `OpenEx` или `Open` функция-член.

Дополнительные сведения о том, как указать источник данных, если это, отличного от заданного с помощью мастера см. в разделе [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) или [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) в *MFC Справочник по*.

##  <a name="_core_disconnecting_from_a_data_source"></a> Отключение от источника данных

Необходимо закрыть любые открытые наборы записей перед вызовом `Close` функцию-член `CDatabase`. В наборах записей, связанных с `CDatabase` объекта необходимо закрыть, все незавершенные `AddNew` или `Edit` отменяются и всех незавершенных транзакций выполняется откат.

#### <a name="to-disconnect-from-a-data-source"></a>Отключение от источника данных

1. Вызовите `CDatabase` объекта [закрыть](../../mfc/reference/cdatabase-class.md#close) функция-член.

1. Уничтожьте объект, только если вы хотите повторно использовать ее.

##  <a name="_core_reusing_a_cdatabase_object"></a> Повторное использование объекта CDatabase

Вы можете повторно использовать `CDatabase` объекта после отключения от него, независимо от используемого для подключения к тому же источнику данных или для подключения к другому источнику данных.

#### <a name="to-reuse-a-cdatabase-object"></a>Повторное использование объекта CDatabase

1. Закройте исходное подключение объекта.

1. Вместо того чтобы уничтожить объект, вызовите его `OpenEx` или `Open` снова функция-член.

## <a name="see-also"></a>См. также

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)