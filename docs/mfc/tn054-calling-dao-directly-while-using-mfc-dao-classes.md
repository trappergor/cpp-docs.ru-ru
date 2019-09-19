---
title: 'TN054: Прямой вызов DAO при использовании классов MFC DAO'
ms.date: 09/17/2019
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
ms.openlocfilehash: cef9852f762a64579e11fe4b0d8606bfc9d36709
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095977"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: Прямой вызов DAO при использовании классов MFC DAO

> [!NOTE]
> DAO используется с базами данных Access и поддерживается в Office 2013. 3,6 является окончательной версией и считается устаревшей. Визуальная C++ среда и мастера не поддерживают DAO (хотя классы DAO включены и их все еще можно использовать). Корпорация Майкрософт рекомендует использовать [шаблоны OLE DB](../data/oledb/ole-db-templates.md) или [ODBC и MFC](../data/odbc/odbc-and-mfc.md) для новых проектов. DAO следует использовать только для поддержки существующих приложений.

При использовании классов баз данных MFC DAO могут возникнуть ситуации, когда необходимо напрямую использовать DAO. Как правило, это не так, но в MFC предоставлены некоторые вспомогательные механизмы для упрощения выполнения прямых вызовов DAO при объединении использования классов MFC с прямыми вызовами DAO. Выполнение прямых вызовов DAO для методов управляемого MFC объекта DAO должно потребовать всего несколько строк кода. Если необходимо создать и использовать объекты DAO, которые *не* управляются MFC, необходимо выполнить немного больше работы, фактически вызвав `Release` объект. В этом техническом примечании объясняется, когда может потребоваться напрямую вызывать DAO, какие возможности вспомогательные методы MFC помогут вам и как использовать интерфейсы DAO OLE. Наконец, в этом примечании представлены примеры функций, демонстрирующих вызов DAO непосредственно для функций безопасности DAO.

## <a name="when-to-make-direct-dao-calls"></a>Когда следует выполнять прямые вызовы DAO

Наиболее распространенные случаи выполнения прямых вызовов DAO при необходимости обновления коллекций или реализации функций, не заключенных в библиотеки MFC. Самой важной функцией, не предоставляемой MFC, является безопасность. Если необходимо реализовать функции безопасности, необходимо напрямую использовать объекты DAO и Group (s). Помимо безопасности, MFC поддерживает только несколько других функций DAO. К ним относятся клонирование набора записей и функции репликации базы данных, а также несколько последних дополнений к DAO.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>Краткий обзор реализации DAO и MFC

Благодаря программированию DAO в MFC упрощается использование DAO за счет обработки множества деталей, поэтому не нужно беспокоиться о некоторых вещах. Сюда входит инициализация OLE, создание и управление объектами DAO (особенно объекты коллекции), проверка ошибок и предоставление строго типизированного, более простого интерфейса (без **варианта** или `BSTR` аргументов). Вы можете выполнять прямые вызовы DAO и по-прежнему использовать преимущества этих функций. Весь код должен выполнять вызов `Release` для любых объектов, созданных прямыми вызовами DAO, и *не* изменять какие-либо указатели интерфейса, которые могут использоваться MFC для внутренних целей. Например, не изменяйте элемент *m_pDAORecordset* открытого `CDaoRecordset` объекта, если не понимаете *все* внутренние последствия. Однако можно использовать интерфейс *m_pDAORecordset* для непосредственного вызова DAO для получения коллекции Fields. В этом случае член *m_pDAORecordset* не будет изменен. По завершении работы с `Release` объектом необходимо просто вызвать метод для объекта коллекции Fields.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>Описание вспомогательных методов для упрощения вызовов DAO

Вспомогательные методы для упрощения вызова DAO — это те же вспомогательные методы, которые используются внутри классов баз данных MFC DAO. Эти вспомогательные методы используются для проверки кодов возврата при выполнении прямого вызова DAO, регистрации выходных данных отладки, проверки ожидаемых ошибок и при необходимости генерации соответствующих исключений. Существует две основные вспомогательные функции и четыре макроса, которые соответствуют одному из этих двух вспомогательных функций. Лучшим объяснением является простое чтение кода. См. раздел **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**и **DAO_TRACE** в афксдао. H, чтобы просмотреть макросы и просмотреть **афксдаочекк** и **афксдаотраце** в даокоре. CPP.

## <a name="using-the-dao-ole-interfaces"></a>Использование интерфейсов DAO OLE

Интерфейсы OLE для каждого объекта в иерархии объектов DAO определяются в файле заголовка ДБДАОИНТ. H, который находится в каталоге \Program Files\Microsoft Visual Studio .NET 2003 \ VC7\include. Эти интерфейсы предоставляют методы, позволяющие управлять всей иерархией DAO.

Для многих методов в интерфейсах DAO необходимо манипулировать `BSTR` объектом (строкой с префиксом длины, используемой в OLE-автоматизации). Объект обычно инкапсулируется в тип данных **Variant.** `BSTR` Сам класс `COleVariant` MFC наследуется от типа данных **Variant** . В зависимости от того, строится ли проект для ANSI или Unicode, интерфейсы DAO будут возвращать ANSI или Unicode `BSTR`. Два макроса, V_BSTR и V_BSTRT, полезны для гарантии того, что интерфейс DAO получает `BSTR` ожидаемый тип.

V_BSTR будет извлекать элемент *бстрвал* объекта `COleVariant`. Этот макрос обычно используется, когда необходимо передать содержимое `COleVariant` в метод интерфейса DAO. В следующем фрагменте кода показаны объявления и фактическое использование двух методов интерфейса DAO Дааусер, которые используют преимущества макроса V_BSTR:

```cpp
COleVariant varOldName;
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

// Code to assign pUser to a valid value omitted DAO 3.6 is the final version and it is considered obsolete.User *pUser = NULL;

// These method declarations were taken from DBDAOINT.H
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;
DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->get_Name(&V_BSTR (&varOldName))); DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```

Обратите внимание `VT_BSTRT` , что аргумент, `COleVariant` указанный в приведенном выше конструкторе, гарантирует `BSTR` , что `COleVariant` в случае сборки версии приложения в кодировке ANSI и Юникод `BSTR` для версии с поддержкой Юникода будет использоваться символ ANSI. приложение. Именно именно это делает DAO.

Другой макрос, V_BSTRT, извлечет элемент `COleVariant` *бстрвал* ANSI или Unicode в зависимости от типа сборки (ANSI или Unicode). В следующем коде показано, как извлечь `BSTR` значение `COleVariant` из `CString`в:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

Макрос V_BSTRT вместе с другими методами открытия других типов, хранящихся в `COleVariant`, показан в примере даовиев. В частности, этот перевод выполняется в `CCrack::strVARIANT` методе. По возможности этот метод преобразует значение `COleVariant` в `CString`экземпляр.

## <a name="simple-example-of-a-direct-call-to-dao"></a>Простой пример прямого вызова DAO

Ситуации могут возникнуть, когда необходимо обновить базовые объекты коллекции DAO. Как правило, это не требуется, но при необходимости это простая процедура. Например, если коллекцию может потребоваться обновить, то при работе в многопользовательской среде с несколькими пользователями создаются новые tabledef. В этом случае коллекция tabledef может устареть. Чтобы обновить коллекцию, необходимо просто вызвать `Refresh` метод определенного объекта коллекции и проверить наличие ошибок:

```cpp DAO 3.6 is the final version and it is considered obsolete._CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Обратите внимание, что в настоящее время все интерфейсы объектов коллекции DAO являются недокументированными сведениями о реализации классов баз данных MFC DAO.

## <a name="using-dao-directly-for-dao-security-features"></a>Использование DAO непосредственно для функций безопасности DAO

Классы базы данных MFC DAO не заносят функции безопасности DAO. Для использования некоторых функций безопасности DAO необходимо вызвать методы интерфейсов DAO. Следующая функция задает системную базу данных, а затем изменяет пароль пользователя. Эта функция вызывает три другие функции, которые впоследствии определяются.

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

В следующих четырех примерах показано, как:

- Задайте системную базу данных DAO (. Файл MDW).

- Задайте пользователя и пароль по умолчанию.

- Изменение пароля пользователя.

- Измените пароль. Файл MDB.

### <a name="setting-the-system-database"></a>Настройка системной базы данных

Ниже приведен пример функции для задания системной базы данных, которая будет использоваться приложением. Эта функция должна вызываться до того, как будут сделаны другие вызовы DAO.

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

### <a name="setting-the-default-user-and-password"></a>Настройка пользователя и пароля по умолчанию

Чтобы задать пользователя и пароль по умолчанию для системной базы данных, используйте следующую функцию:

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

### <a name="changing-the-password-of-an-mdb-file"></a>Изменение пароля. Файл MDB

Для изменения пароля. Файл MDB, используйте следующую функцию:

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

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
