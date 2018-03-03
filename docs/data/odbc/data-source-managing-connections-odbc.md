---
title: "Источник данных: Управление соединениями (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b83093496d355fdba8b5d714875d08040ae28ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-managing-connections-odbc"></a>Источник данных. Управление соединениями (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Содержание раздела:  
  
-   [Настройка источника данных](#_core_configuring_a_data_source).  
  
-   [Воздействие многопользовательской среды на источник данных и его наборы записей](#_core_working_in_a_multiuser_environment).  
  
-   [Почему в создании строки подключения к источнику данных](#_core_generalizing_the_connection_string).  
  
-   [Подключение к источнику данных](#_core_connecting_to_a_specific_data_source).  
  
-   [Отключение от источника данных](#_core_disconnecting_from_a_data_source).  
  
-   [Как повторно использовать объект CDatabase](#_core_reusing_a_cdatabase_object).  
  
 Подключение к источнику данных предполагает установление соединения с СУБД для доступа к данным. При подключении к источнику данных из приложения с помощью драйвера ODBC, драйвер производит подключение, локально или по сети.  
  
 Можно подключиться к любому источнику данных, для которой имеется драйвер ODBC. Пользователи приложения также должны иметь один и тот же драйвер ODBC для источника данных. Дополнительные сведения о распространении драйверов ODBC см. в разделе [распространение компонентов ODBC среди клиентов Your](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a>Настройка источника данных  
 Администратор ODBC используется для настройки источников данных. Администратор ODBC после установки можно также использовать для добавления или удаления источников данных. При создании приложений, либо можно направлять пользователей для администратора ODBC с помощью которых можно добавить источники данных или эту функциональность можно встраивать в приложение, выполнение прямых вызовов установки ODBC. Дополнительные сведения см. в разделе [администратор ODBC](../../data/odbc/odbc-administrator.md).  
  
 Файл Excel можно использовать в качестве источника данных, и необходимо настроить файл, чтобы он зарегистрирован и отображается в **Выбор источника данных** диалоговое окно.  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>Использование файла Excel в качестве источника данных  
  
1.  Настройка файла с помощью администратора источника данных ODBC.  
  
2.  На **файловый DSN** щелкните **добавить**.  
  
3.  В **Создание нового источника данных** диалоговое окно, выберите драйвер Excel, а затем нажмите кнопку **Далее**.  
  
4.  Нажмите кнопку **Обзор**и выберите имя файла для использования в качестве источника данных.  
  
> [!NOTE]
>  Может потребоваться выбрать **все файлы** в раскрывающемся меню, чтобы отобразить XLS-файлы.  
  
1.  Щелкните **Далее**и затем нажмите кнопку **Готово**.  
  
2.  В **Настройка ODBC Microsoft Excel** диалогового окна выберите версию базы данных и книги.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a>Работа в многопользовательской среде  
 Если несколько пользователей подключены к источнику данных, они могут изменять данные, а при работе с ней в наборе данных. Аналогичным образом изменения могут повлиять на наборы записей других пользователей. Дополнительные сведения см. в разделе [набор записей: как наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) и [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a>Создание обобщенной строки подключения  
 Мастеры использовать строку подключения по умолчанию для установления соединения с источником данных. Используйте это соединение позволяет просматривать таблицы и столбцы, при разработке приложения. Тем не менее эта строка подключения по умолчанию могут не подходить для пользовательских подключений к источнику данных через приложение. Например источник данных и путь к нему может отличаться от используемого при разработке приложения. В этом случае следует реализовать [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) член работать более универсальный код и удалить реализацию мастера. Например используйте один из следующих подходов:  
  
-   Регистрация и управление строками подключения, с помощью администратора ODBC.  
  
-   Измените строку подключения и удалите имя источника данных. Структура предоставляет ODBC в качестве источника данных. во время выполнения ODBC выводит диалоговое окно с запросом данных источника имя и любые другие необходимые сведения для соединения.  
  
-   Укажите только имя источника данных. ODBC запрашивает идентификатор пользователя и пароль, если это необходимо. Например строку подключения перед обобщения, выглядит следующим образом:  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     Эта строка подключения указывает доверенного соединения, которое использует средства безопасности Windows NT. Не следует жестко кодировать пароль или указание пустого пароля, так как это создает уязвимости в системе безопасности основной. Вместо этого можно предоставить `GetDefaultConnect` новую строку подключения, чтобы она запрашивает идентификатор пользователя и пароль.  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a>Подключение к определенному источнику данных  
 Чтобы подключиться к определенному источнику данных, источник данных должен уже были настроены с [администратор ODBC](../../data/odbc/odbc-administrator.md).  
  
#### <a name="to-connect-to-a-specific-data-source"></a>Для подключения к определенному источнику данных  
  
1.  Создать `CDatabase` объекта.  
  
2.  Вызовите его `OpenEx` или **откройте** функции-члена.  
  
 Дополнительные сведения о том, как указать источник данных, если это нечто, отличное от указанного вами с помощью мастера см. в разделе [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) или [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) в *MFC Справочник по*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a>Отключение от источника данных  
 Необходимо закрыть все открытые наборы записей перед вызовом **закрыть** функции-члена `CDatabase`. В наборах записей, связанных с `CDatabase` объекта необходимо закрыть, все ожидающие `AddNew` или **изменить** отменяются и всех незавершенных транзакций будет выполнен откат.  
  
#### <a name="to-disconnect-from-a-data-source"></a>Отключение от источника данных  
  
1.  Вызовите `CDatabase` объекта [закрыть](../../mfc/reference/cdatabase-class.md#close) функции-члена.  
  
2.  Если не требуется использовать его, удалите этот объект.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a>Повторное использование объекта CDatabase  
 Можно повторно использовать `CDatabase` объекта после отключения от него, независимо от используемого для повторного подключения к тому же источнику данных или для подключения к другому источнику данных.  
  
#### <a name="to-reuse-a-cdatabase-object"></a>Чтобы повторно использовать объект CDatabase  
  
1.  Закройте исходное подключение объекта.  
  
2.  Вместо того чтобы уничтожить объект, вызовите его `OpenEx` или **откройте** снова функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Источник данных: Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)