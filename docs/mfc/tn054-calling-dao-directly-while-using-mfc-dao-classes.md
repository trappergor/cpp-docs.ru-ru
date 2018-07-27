---
title: 'TN054: Вызов DAO напрямую при использовании классов MFC DAO | Документы Microsoft'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dao
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f060364a8c08a32acae49a0386911486251b0e31
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122455"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054. Вызов DAO напрямую при использовании классов DAO MFC

> [!NOTE]
> Среда Visual C++ и мастера не поддерживают DAO (хотя классы DAO включены и их можно по-прежнему использовать). Корпорация Майкрософт рекомендует использовать [шаблонов OLE DB](../data/oledb/ole-db-templates.md) или [ODBC и MFC](../data/odbc/odbc-and-mfc.md) для новых проектов. DAO следует использовать только для поддержки существующих приложений.

При использовании классов MFC DAO базы данных, могут возникнуть ситуации, где это необходимо, чтобы непосредственно использовать DAO. Как правило это будет не так, но предоставляет некоторые вспомогательные механизмы для упрощения прямого DAO вызовах простой при объединении с использованием классов MFC с прямыми вызовами DAO MFC. Делая прямой DAO вызовы методов объекта управляемого MFC DAO требуется всего несколько строк кода. Если необходимо создать и использовать объекты DAO, *не* управляется MFC, необходимо будет сделать небольшую дополнительную работу, вызвав фактически `Release` в объекте. Это техническое Примечание объясняется, когда может потребоваться непосредственный вызов DAO MFC помощники можно сделать помогут вам и способы использования интерфейсов DAO OLE. Наконец эта заметка предоставляет некоторые функции пример, демонстрирующий вызов DAO напрямую для функций безопасности DAO.

## <a name="when-to-make-direct-dao-calls"></a>Когда следует выполнять вызовы прямой DAO

Наиболее распространенные ситуации для выполнение прямых вызовов DAO возникают, когда коллекции должны обновляться или при реализации функций, не упакованные MFC. Наиболее важная функция, не предоставляемые MFC является безопасности. Если вы хотите реализовать функции безопасности, необходимо напрямую использовать объекты DAO пользователей и групп. Помимо безопасности имеется только несколько других DAO возможностей не поддерживается в MFC. К ним относятся функции набора записей клонирования и базы данных репликации, а также несколько позднего дополнения для DAO.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>Общие сведения о реализации DAO и MFC

Перенос MFC DAO упрощает использование DAO проще путем обработки различные аспекты, поэтому не нужно беспокоиться о основные операции. Это включает инициализацию OLE, создание и управление объектов DAO (особенно объекты коллекции), ошибки проверки и предоставляя строго типизированные, более простой интерфейс (не **VARIANT** или `BSTR` аргументы). Можно внести прямые вызовы DAO и воспользоваться преимуществами этих функций. Все должен выполнить программный код является вызовом `Release` любые объекты, созданные путем прямого DAO вызывает и *не* изменять какие-либо указателей интерфейса, которые внутренне MFC может зависеть от. Например, не изменяйте *m_pDAORecordset* открытый член `CDaoRecordset` объекта, если только вы не знаете *все* внутренней возможные последствия. Тем не менее, можно выполнить *m_pDAORecordset* интерфейс вызов DAO напрямую для получения коллекции полей. В этом случае *m_pDAORecordset* член не будет изменяться. Необходимо просто вызвать `Release` на объекты коллекции полей, когда вы закончите с объектом.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>Описание вспомогательных методов, чтобы сделать DAO вызывает проще

Вспомогательные методы, позволяет сделать вызов DAO проще — же поддержки для внутреннего использования в классы баз данных MFC DAO. Эти вспомогательные методы позволяют проверку кодов, возвращаемых при выполнении прямой вызов DAO, ведение журнала отладки, проверки ожидаемые ошибки и создание соответствующего исключений, при необходимости. Существует две вспомогательные функции для базового и четыре макросов, которые сопоставляются с одним из этих двух вспомогательных методов. Наиболее объяснение бы просто чтение кода. В разделе **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, и **DAO_TRACE** в AFXDAO. H, чтобы показать макросы и просмотреть **AfxDaoCheck** и **AfxDaoTrace** в DAOCORE. CPP.

## <a name="using-the-dao-ole-interfaces"></a>С помощью интерфейсов OLE DAO

Интерфейсы OLE для каждого объекта в иерархии объектов DAO, определяются в файле заголовка DBDAOINT. (H), которая находится в каталоге \Program Files\Microsoft 2003\VC7\include Visual Studio .NET. Эти интерфейсы обеспечивают методы, позволяющие управлять всей иерархии DAO.

Для многих методов в интерфейсах DAO необходимо манипулировать `BSTR` объекта (длина префикса строка, используемая в OLE-автоматизация). `BSTR` Обычно инкапсулируется в объект **VARIANT** тип данных. Класс MFC `COleVariant` сам наследует от **VARIANT** тип данных. В зависимости от того, является ли построения проекта для ANSI или Юникод, ANSI или Юникод будет возвращать интерфейсы DAO `BSTR`s. Два макроса, V_BSTR и V_BSTRT, могут быть полезны обеспечение интерфейс DAO возвращает `BSTR` ожидаемого типа.

Извлечь V_BSTR *bstrVal* членом `COleVariant`. Этот макрос обычно используется, когда нужно передать содержимое `COleVariant` метода интерфейса DAO. В следующем фрагменте кода показаны объявления и фактическое использование для двух методов интерфейса DAO DAOUser, использующие преимущества V_BSTR макрос:

```cpp
COleVariant varOldName;
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

// Code to assign pUser to a valid value omitted
DAOUser *pUser = NULL;

// These method declarations were taken from DBDAOINT.H
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;

DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));
DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```

Обратите внимание, что `VT_BSTRT` аргумент, указанный в `COleVariant` выше конструктор гарантирует, что будет ANSI `BSTR` в `COleVariant` при построении версия ANSI, Юникод и приложения `BSTR` для версии Юникода ваше приложение. Это требует DAO.

Другие макрос, V_BSTRT, будут извлечены ANSI или Юникода *bstrVal* членом `COleVariant` в зависимости от типа сборки (ANSI или Юникод). В следующем коде показано, как извлечь `BSTR` значение из `COleVariant` в `CString`:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

Макрос V_BSTRT, вместе с другими методами, чтобы открыть другие типы, которые хранятся в `COleVariant`, показано в образце DAOVIEW. В частности, такое преобразование выполняется в `CCrack::strVARIANT` метод. Этот метод, если это возможно, преобразует значение `COleVariant` в экземпляр `CString`.

## <a name="simple-example-of-a-direct-call-to-dao"></a>Простой пример прямой вызов DAO

Могут возникать ситуации, когда необходимо обновить базовой коллекции объектов DAO. Как правило это должен быть необходимо, но это простая процедура, если это необходимо. Пример когда коллекции может потребоваться для обновления — при работе в многопользовательской среде с несколькими пользователями, создание новых tabledefs. В этом случае tabledefs-коллекция может стать неактуальной. Для обновления коллекции, необходимо просто вызвать `Refresh` метод определенной коллекции объектов и проверяет наличие ошибок:

```cpp
DAO_CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Обратите внимание, что в настоящее время все интерфейсы объекта DAO коллекции недокументированные реализации классов MFC DAO базы данных.

## <a name="using-dao-directly-for-dao-security-features"></a>С помощью DAO непосредственно для DAO функции безопасности

Классы баз данных MFC DAO не заключайте функции безопасности DAO. Необходимо вызывать методы интерфейсов DAO некоторые возможности безопасности DAO. Следующая функция задает системную базу данных и затем изменяет пароль пользователя. Эта функция вызывает три других функций, которые определены в дальнейшем.

```cpp
void ChangeUserPassword()
{
    // Specify path to the Microsoft Access *// system database
    CString strSystemDB =
        _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

    // Set system database before MFC initilizes DAO
    // NOTE: An MFC module uses only one instance
    // of a DAO database engine object. If you have
    // called a DAO object in your application prior
    // to calling the function below, you must call
    // AfxDaoTerm to destroy the existing database
    // engine object. Otherwise, the database engine
    // object already in use will be reused, and setting
    // a system datbase will have no effect.
    //
    // If you have used a DAO object prior to calling
    // this function it is important that DAO be
    // terminated with AfxDaoTerm since an MFC
    // module only gets one copy of the database engine
    // and that engine will be reused if it hasn't been
    // terminated. In other words, if you do not call
    // AfxDaoTerm and there is currently a database
    // initialized, setting the system database will
    // have no effect.
    SetSystemDB(strSystemDB);

    // User name and password manually added
    // by using Microsoft Access
    CString strUserName = _T("NewUser");
    CString strOldPassword = _T("Password");
    CString strNewPassword = _T("NewPassword");

    // Set default user so that MFC will be able
    // to log in by default using the user name and
    // password from the system database
    SetDefaultUser(strUserName, strOldPassword);

    // Change the password. You should be able to
    // call this function from anywhere in your
    // MFC application
    ChangePassword(strUserName, strOldPassword, strNewPassword);

    // ...
}
```

Следующие четыре примеры демонстрируют, как:

- Перевод базы данных DAO системы (. MDW-файл).

- Значение по умолчанию пользователя и пароль.

- Изменение пароля пользователя.

- Изменение пароля. MDB-файлу.

### <a name="setting-the-system-database"></a>Установка системной базы данных

Ниже приведен пример функции, чтобы установить системную базу данных, который будет использоваться приложением. Эта функция должна вызываться перед внесением каких-либо других вызовов DAO.

```cpp
// Set the system database that the
// DAO database engine will use

void SetSystemDB(CString& strSystemMDB)
{
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

    // Initialize DAO for MFC
    AfxDaoInit();
    DAODBEngine* pDBEngine = AfxDaoGetEngine();

    ASSERT(pDBEngine != NULL);

    // Call put_SystemDB method to set the *// system database for DAO engine
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));
}
```

### <a name="setting-the-default-user-and-password"></a>Настройка стандартной учетной записи и пароль

Для установки по умолчанию пользователя и пароль для системной базы данных, используйте следующую функцию:

```cpp
void SetDefaultUser(CString& strUserName,
    CString& strPassword)
{
    COleVariant varUserName(strUserName, VT_BSTRT);
    COleVariant varPassword(strPassword, VT_BSTRT);

    DAODBEngine* pDBEngine = AfxDaoGetEngine();
    ASSERT(pDBEngine != NULL);

    // Set default user:
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

    // Set default password:
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));
}
```

### <a name="changing-a-users-password"></a>Изменение пароля пользователя

Чтобы изменить пароль пользователя, используйте следующую функцию:

```cpp
void ChangePassword(CString &strUserName,
    CString &strOldPassword,
    CString &strNewPassword)
{
    // Create (open) a workspace
    CDaoWorkspace wsp;
    CString strWspName = _T("Temp Workspace");

    wsp.Create(strWspName, strUserName, strOldPassword);
    wsp.Append();

    // Determine how many objects there are *// in the Users collection
    short nUserCount;
    short nCurrentUser;
    DAOUser *pUser = NULL;
    DAOUsers *pUsers = NULL;

    // Side-effect is implicit OLE AddRef()
    // on DAOUser object:
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

    // Side-effect is implicit OLE AddRef()
    // on DAOUsers object
    DAO_CHECK(pUsers->getcount(&nUserCount));

    // Traverse through the list of users
    // and change password for the userid
    // used to create/open the workspace
    for(nCurrentUser = 0; nCurrentUser <nUserCount; nCurrentUser++)
    {
        COleVariant varIndex(nCurrentUser, VT_I2);
        COleVariant varName;

        // Retrieve information for user nCurrentUser
        DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

        // Retrieve name for user nCurrentUser
        DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

        CString strTemp = V_BSTRT(&varName);

        // If there is a match, change the password
        if (strTemp == strUserName)
        {
            COleVariant varOldPwd(strOldPassword, VT_BSTRT);
            COleVariant varNewPwd(strNewPassword, VT_BSTRT);

            DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd),
                V_BSTR(&varNewPwd)));

            TRACE("\t Password is changed\n");
        }
    }
    // Clean up: decrement the usage count
    // on the OLE objects
    pUser->Release();
    pUsers->Release();
    wsp.Close();
}
```

### <a name="changing-the-password-of-an-mdb-file"></a>Изменение пароля. MDB-файлу

Чтобы изменить пароль. MDB файла следует использовать следующую функцию:

```cpp
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)
{
    CDaoDatabase db;
    CString strConnect(_T(";pwd="));

    // the database must be opened as exclusive
    // to set a password
    db.Open(pDB, TRUE, FALSE, strConnect + pszOldPassword);

    COleVariant NewPassword(pszNewPassword, VT_BSTRT),
                OldPassword(pszOldPassword, VT_BSTRT);

    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword),
        V_BSTR(&NewPassword)));

    db.Close();
}
```

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)  
[Технические примечания по категории](../mfc/technical-notes-by-category.md)  
