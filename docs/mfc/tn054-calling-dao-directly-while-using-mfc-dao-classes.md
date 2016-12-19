---
title: "TN054. Вызов DAO напрямую при использовании классов DAO MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dao"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "доступ к данным DAO.NET, и MFC"
  - "доступ к данным DAO.NET, прямой вызов"
  - "доступ к данным DAO.NET, безопасность"
  - "MFC [C++], DAO и"
  - "пароли [C++], вызов DAO"
  - "безопасность [MFC]"
  - "безопасность [MFC], DAO"
  - "TN054"
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN054. Вызов DAO напрямую при использовании классов DAO MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Что касается Visual C\+\+ .NET, то среда и мастера Visual C\+\+ больше не поддерживают DAO \(хотя классы DAO включены и вы по\-прежнему можете их использовать\).  Майкрософт рекомендует использовать [Шаблоны OLE DB](../Topic/OLE%20DB%20Templates.md) или [ODBC и MFC](../data/odbc/odbc-and-mfc.md) для новых проектов.  DAO необходимо использовать только для поддержки существующих приложений.  
  
 При использовании классов баз данных MFC DAO, могут возникнуть ситуации, когда необходимо использовать DAO напрямую.  Обычно это неприменимо, но MFC предоставляется некоторые механизмы поддержки для упрощения вызывать непосредственно DAO простым, сочетающий использование классов MFC DAO непосредственно с вызовами.  Выполнение прямых вызовов методов DAO в образце управлениеого объекта должен DAO требуется только несколько строк кода.  Если необходимо создать и использовать объекты, управляемых MFC DAO, не следует делать несколько больше работы является вызов метода **Выпуск** для объекта.  Это объясняется техническое примечание при необходимости вызова DAO напрямую, что вспомогательные MFC могут сделать, чтобы помочь и как использовать интерфейсы OLE DAO.  Наконец, эта заметка предоставляет некоторые функции пример, показывающий, как вызова DAO непосредственно для функций безопасности DAO.  
  
## Если он непосредственно DAO  
 Наиболее распространенные ситуации для создания непосредственно DAO возникают, когда коллекции необходимо обновить или при реализации функции не созданных программу\-оболочку MFC.  Функция не значительно представленной MFC безопасности.  Если необходимо реализовать функции безопасности, необходимо использовать объекты пользователей и групп DAO напрямую.  Помимо безопасности, существует несколько других функций, не поддерживаемых MFC DAO.  Эти функции включают клонирования и репликации базы данных набора записей, так и нескольких последних добавлений в DAO.  
  
## Краткий обзор реализации DAO и MFC  
 Обертывание MFC DAO делает использование DAO проще, обработки множества данных, поэтому не нужно беспокоиться о маленьких действиях.  Это включает инициализацию OLE, создания и управления объектов DAO \(особенно объектов коллекции\), проверки ошибок, а также являются строго типизированными, более простой интерфейс \(нет **VARIANT** или аргументы `BSTR` \).  Можно напрямую осуществляет DAO и по\-прежнему воспользоваться преимуществами этих функций.  Весь код должен выполнить вызов метода **Выпуск** для всех объектов, созданных непосредственно вызовами DAO и не любое изменение указателей интерфейса, MFC может полагаться на внутренне.  Например, не изменяйте элемент **m\_pDAORecordset** открытого объекта `CDaoRecordset`, если вы не знаете внутренних последствий.  Можно, однако, использовать интерфейс **m\_pDAORecordset** для вызова DAO непосредственно для получения коллекции полей.  В этом случае элемент **m\_pDAORecordset** не может быть изменен.  Следует просто должны вызывать **Выпуск** для объекта коллекции полей после окончания работы с объектом.  
  
## Описание вспомогательных обращаться DAO проще.  
 Вспомогательные, предоставленных и вызова DAO проще те же вспомогательные, предназначенные для внутреннего использования в классах баз данных MFC DAO.  Эти вспомогательные используются для проверки коды возврата звоня непосредственно DAO, в файл журнала вывод отладки, допустимых для проверки ошибок и соответствующие при порождении исключения при необходимости.  2 Основных вспомогательной функции и 4 макроса, сопоставляют одно из этих 2 вспомогательных.  Наилучшее объяснение будет просто чтение кода.  В разделе **DAO\_CHECK**, **DAO\_CHECK\_ERROR**, **DAO\_CHECK\_MEM** и **DAO\_TRACE** в AFXDAO.H для просмотра макросы и см. **AfxDaoCheck** и **AfxDaoTrace** в DAOCORE.CPP.  
  
## С помощью интерфейсов OLE DAO  
 Интерфейсов OLE для каждого объекта в иерархии объектов DAO определены в файле заголовка DBDAOINT.H, который находится в каталоге Files\\Microsoft Visual Studio .NET 2003\\VC7\\include \\Program.  Эти интерфейсы предоставляют методы, позволяющие управлять всей иерархии DAO.  
  
 Для многих методов в интерфейсах DAO потребуется манипулированию объектом `BSTR` \(длина\- присоединенную префикса строку, используемую в ole\-автоматизацией\).  Объект `BSTR` обычно инкапсулированы в тип данных **VARIANT**.  Класс `COleVariant` само MFC унаследован от типа данных **VARIANT**.  В зависимости от того откуда выполняется проекта для ANSI или юникода, интерфейсы DAO возвращают ANSI или юникод `BSTR` s.  2 Макроса, **V\_BSTR** и **V\_BSTRT**, используются для убеждать, интерфейс DAO получает `BSTR` ожидаемого типа.  
  
 **V\_BSTR** извлекает элемент **bstrVal**`COleVariant`.  Этот макрос обычно используется, когда требуется передать содержимое `COleVariant` метода интерфейса DAO.  В следующем фрагменте кода показано и объявления и фактическое использование для 2 методов интерфейса DAO DAOUser, пользующихся преимуществами макроса **V\_BSTR**:  
  
```  
COleVariant varOldName;  
COleVariant varNewName( _T("NewUser"), VT_BSTRT );  
  
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
  
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
  
DAO_CHECK( pUser->get_Name( &V_BSTR ( &varOldName ) ));  
DAO_CHECK( pUser->put_Name( V_BSTR ( &varNewName ) ));  
```  
  
 Обратите внимание, что аргумент `VT_BSTRT`, указанный в конструкторе `COleVariant` предыдущем гарантирует, что будет ANSI `BSTR` в `COleVariant` при построении версии ANSI приложения и юникод `BSTR` для юникода версии приложения.  Что такое DAO ожидает.  
  
 Другой макрос, **V\_BSTRT** извлекает или член ANSI или юникода **bstrVal**`COleVariant` в зависимости от типа построения \(ANSI или юникод\).  В следующем примере демонстрируется, как получить `BSTR` значение из `COleVariant` в `CString`:  
  
```  
COleVariant varName( _T( "MyName" ), VT_BSTRT );  
CString str = V_BSTRT( &varName );  
```  
  
 Макрос **V\_BSTRT** вместе с другими методами, чтобы открыть других типов, которые хранятся в `COleVariant`, как показано в примере DAOVIEW.  В частности, этот преобразование выполняется в методе **CCrack::strVARIANT**.  Этот метод, если это возможно, преобразует значение `COleVariant` в экземпляр `CString`.  
  
## Простой пример прямого вызова DAO  
 Могут возникнуть ситуации, когда необходимо обновить базовые объекты коллекции DAO.  Обычно это не должно быть обязательным, но простую процедуру, если это необходимо.  Пример, когда коллекция может обновлять при работе в многопользовательской среде с нескольких пользователей создания новых tabledefs.  В этом случае коллекция tabledefs может быть несвежой.  Для обновления коллекции необходимо просто вызвать метод **Обновить** определенного объекта коллекции и проверить ошибки:  
  
```  
DAO_CHECK( pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh( ) );  
```  
  
 Обратите внимание, что в данный момент все интерфейсы объекта коллекции DAO незадокументированные подробности реализации классов баз данных MFC DAO.  
  
## С помощью классов DAO непосредственно для функций безопасности DAO  
 Классы баз данных MFC DAO не реализует функции безопасности DAO.  Необходимо вызывать методы интерфейсов DAO использовать некоторые функции безопасности DAO.  Следующая функция задает базу данных системы и затем изменить пароль пользователя.  Этот метод вызывает функции 3 других функций, которая затем определены.  
  
```  
void ChangeUserPassword( )  
{  
   // Specify path to the Microsoft Access  
   // system database  
   CString strSystemDB =   
     _T( "c:\\Program Files\\MSOffice\\access\\System.mdw" );  
  
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
   // have no affect.  
  
   SetSystemDB( strSystemDB );  
  
   // User name and password manually added  
   // by using Microsoft Access  
   CString strUserName = _T( "NewUser" );  
   CString strOldPassword = _T( "Password" );  
   CString strNewPassword = _T( "NewPassword" );  
  
   // Set default user so that MFC will be able  
   // to log in by default using the user name and   
   // password from the system database  
   SetDefaultUser( strUserName, strOldPassword );  
  
   // Change the password. You should be able to  
   // call this function from anywhere in your   
   // MFC application  
   ChangePassword( strUserName, strOldPassword,   
                   strNewPassword );  
  
   .  
   .  
   .  
  
}  
```  
  
 Следующие 4 примера демонстрируется на:  
  
-   Задайте базу данных системы DAO \(файл .MDW\).  
  
-   Задайте пользователя по умолчанию и пароль.  
  
-   Измените пароль пользователя.  
  
-   Измените пароль файла .MDB.  
  
### Параметр базы данных система  
 Функция ниже примера, чтобы установить базу данных системы, которая будет использоваться приложением.  Эту функцию необходимо вызывать перед любыми другими DAO выполненные.  
  
```  
// Set the system database that the   
// DAO database engine will use  
  
void SetSystemDB( CString & strSystemMDB )  
{  
   COleVariant varSystemDB( strSystemMDB, VT_BSTRT );  
  
   // Initialize DAO for MFC  
   AfxDaoInit( );  
   DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  
   ASSERT( pDBEngine != NULL );  
  
   // Call put_SystemDB method to set the   
   // system database for DAO engine  
   DAO_CHECK( pDBEngine->put_SystemDB( varSystemDB.bstrVal ) );  
}  
```  
  
### Параметр по умолчанию пользователя и пароль  
 Чтобы задать пользователя по умолчанию и пароль для базы данных системы используйте следующую функцию:  
  
```  
void SetDefaultUser(CString & strUserName, CString & strPassword)  
{  
  COleVariant varUserName( strUserName, VT_BSTRT );  
  COleVariant varPassword( strPassword, VT_BSTRT );  
  
  DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  ASSERT( pDBEngine != NULL );  
  
  // Set default user:  
  DAO_CHECK( pDBEngine->put_DefaultUser( varUserName.bstrVal ) );  
  
  // Set default password:  
  DAO_CHECK( pDBEngine->put_DefaultPassword( varPassword.bstrVal ) );  
}  
```  
  
### Изменение пароля пользователя  
 Чтобы изменить пароль пользователя, используйте следующую функцию:  
  
```  
void ChangePassword( CString &strUserName,   
                     CString &strOldPassword,   
                     CString &strNewPassword )  
{  
   // Create (open) a workspace  
   CDaoWorkspace wsp;  
   CString strWspName = _T( "Temp Workspace" );  
  
   wsp.Create( strWspName, strUserName,  
               strOldPassword );  
   wsp.Append( );  
  
   // Determine how many objects there are  
   // in the Users collection  
   short nUserCount;  
   short nCurrentUser;  
   DAOUser *pUser  = NULL;  
   DAOUsers *pUsers = NULL;  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUser object:  
   DAO_CHECK( wsp.m_pDAOWorkspace->get_Users( &pUsers ) );  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUsers object  
    DAO_CHECK( pUsers->get_Count( &nUserCount ) );  
  
   // Traverse through the list of users   
   // and change password for the userid  
   // used to create/open the workspace  
   for( nCurrentUser = 0; nCurrentUser < nUserCount;  
        nCurrentUser++ )  
   {  
       COleVariant varIndex( nCurrentUser, VT_I2 );  
       COleVariant varName;  
  
       // Retrieve information for user nCurrentUser  
       DAO_CHECK( pUsers->get_Item( varIndex, &pUser ) );  
  
       // Retrieve name for user nCurrentUser  
       DAO_CHECK( pUser->get_Name( &V_BSTR( &varName ) ) );  
  
       CString strTemp = V_BSTRT( &varName );  
  
       // If there is a match, change the password  
       if( strTemp == strUserName )  
       {  
           COleVariant varOldPwd( strOldPassword,   
                                  VT_BSTRT );  
           COleVariant varNewPwd( strNewPassword,   
                                  VT_BSTRT );  
  
           DAO_CHECK( pUser->NewPassword( V_BSTR( &varOldPwd ),  
                      V_BSTR( &varNewPwd ) ) );  
  
           TRACE( "\t Password is changed\n" );  
       }  
   }  
  
   // Clean up: decrement the usage count  
   // on the OLE objects  
   pUser->Release( );  
   pUsers->Release( );  
  
   wsp.Close( );  
}  
```  
  
### Изменение пароля файла .MDB  
 Чтобы изменить пароль файла .MDB используйте следующую функцию:  
  
```  
void SetDBPassword( LPCTSTR pDB, LPCTSTR pszOldPassword, LPCTSTR pszNewPassword )  
{  
   CDaoDatabase db;  
   CString strConnect( _T( ";pwd=" ) );  
  
   // the database must be opened as exclusive  
   // to set a password  
   db.Open( pDB, TRUE, FALSE,   
            strConnect + pszOldPassword );  
  
   COleVariant NewPassword( pszNewPassword, VT_BSTRT ),  
               OldPassword( pszOldPassword, VT_BSTRT );  
  
   DAO_CHECK( db.m_pDAODatabase->NewPassword( V_BSTR( &OldPassword ),  
              V_BSTR( &NewPassword ) ) );  
  
   db.Close();  
}  
```  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)