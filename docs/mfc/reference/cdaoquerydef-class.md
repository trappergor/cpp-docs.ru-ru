---
title: "Класс CDaoQueryDef | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- QueryDef objects
- CDaoQueryDef class
- queries [Visual Studio], defining
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0bf06c68bb7072aa1907e4c730848cca9ff5e7d0
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoquerydef-class"></a>Класс CDaoQueryDef
Представляет определение запроса или QueryDef, как правило, сохраненный в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Создает **CDaoQueryDef** объекта. Затем вызовите метод **откройте** или **создать**, в зависимости от потребностей.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|Добавляет querydef QueryDefs-коллекция базы данных как сохраненный запрос.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если запрос можно обновить базу данных.|  
|[CDaoQueryDef::Close](#close)|Закрывает объект querydef. После завершения работы с его, удаляет этот объект C++.|  
|[CDaoQueryDef::Create](#create)|Создает объект базового querydef DAO. Используйте querydef как временный запрос или вызов **Append** сохранить его в базе данных.|  
|[CDaoQueryDef::Execute](#execute)|Выполняет запрос, определенный объектом querydef.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Возвращает строку подключения, связанную с querydef. Строка подключения определяет источник данных. (Для SQL передаваемых запросов только; в противном случае — пустая строка.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Возвращает дату создания сохраненного запроса.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату последнего обновления сохраненного запроса.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Возвращает количество полей, определенных querydef.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Возвращает сведения о указанного поля, определенные в запросе.|  
|[CDaoQueryDef::GetName](#getname)|Возвращает имя querydef.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Возвращает значение времени ожидания, используемые ODBC (для запроса ODBC) при выполнении querydef. Это определяет, как долго для завершения действия запроса.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Возвращает число параметров, определенные для запроса.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Возвращает сведения о указанный параметр в запрос.|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Возвращает значение указанного параметра запроса.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Возвращает количество записей, затронутых запросом.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Возвращает ненулевое значение, если определяется querydef запрос возвращает записи.|  
|[CDaoQueryDef::GetSQL](#getsql)|Возвращает строку SQL, определяет запрос, определяется querydef.|  
|[CDaoQueryDef::GetType](#gettype)|Возвращает тип запроса: удаление, обновление, добавление, создание таблицы и так далее.|  
|[CDaoQueryDef::IsOpen](#isopen)|Возвращает ненулевое значение, если querydef открытым и может быть выполнено.|  
|[CDaoQueryDef::Open](#open)|Открытие существующего querydef хранится в базе данных QueryDefs.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Задает строку подключения для запроса к серверу на источнике данных ODBC.|  
|[CDaoQueryDef::SetName](#setname)|Задает имя сохраненного запроса, заменив имя используется при создании querydef.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Задает значение времени ожидания, используемые ODBC (для запроса ODBC) при выполнении querydef.|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Задает значение указанного параметра в запрос.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Определяет, возвращает ли querydef записей. Задав этому атрибуту значение **TRUE** допустимо только для запросов к серверу.|  
|[CDaoQueryDef::SetSQL](#setsql)|Задает строку SQL, определяет запрос, определяется querydef.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Указатель на интерфейс OLE для базового объекта querydef DAO.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Указатель на `CDaoDatabase` объект, с которым связан querydef. Querydef может сохраняться в базе данных или нет.|  
  
## <a name="remarks"></a>Примечания  
 Querydef является объект доступа к данным, который содержит инструкцию SQL, описывающую запрос и его свойства, такие как «Дата создания» и «Время ожидания ODBC». Можно также создать временный querydef объектов без сохранения, но он является удобным — и намного эффективнее — сохранять часто повторно использовать запросы в базе данных. Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект поддерживает коллекцию, вызывается QueryDefs, содержащую коллекцию его сохраненного querydefs.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Можно по-прежнему обращаться к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классов MFC на основе ODBC; классы на основе DAO доступны данные, включая посредством драйверов ODBC, через свои собственные компонента database engine. Классы на основе DAO также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, без непосредственного вызова DAO.  
  
## <a name="usage"></a>Использование  
 Сохраненные с помощью querydef объектов либо для работы с существующим сохраненный запрос или создайте новый запрос или временный запрос:  
  
1.  Во всех случаях сначала конструируется `CDaoQueryDef` объекта, указав указатель [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта, которому принадлежит запрос.  
  
2.  Затем выполните следующую команду, в зависимости от того, что нужно:  
  
    -   Чтобы использовать существующий сохраненный запрос, вызов объекта querydef [откройте](#open) функция-член, указав имя сохраненного запроса.  
  
    -   Чтобы создать новый сохраненный запрос, вызовите объекта querydef [создать](#create) функция-член, указав имя запроса. Затем вызовите [Append](#append) сохранить запрос путем добавления его к коллекции QueryDefs базы данных. **Создание** помещает querydef в открытом состоянии, поэтому после вызова метода **создать** не следует вызывать **откройте**.  
  
    -   Чтобы создать временный querydef, вызовите **создать**. Необходимо передайте пустую строку для имени запроса. Не следует вызывать **Append**.  
  
 После завершения использования объекта querydef, вызвать его [закрыть](#close) члена функции; затем удаление объекта querydef.  
  
> [!TIP]
>  Для их создания и сохранения их в базе данных Microsoft Access является самым простым способом создания сохраненных запросов. Затем можно открыть и использовать их в коде MFC.  
  
## <a name="purposes"></a>В целях  
 Можно использовать объект querydef для любого из следующих целей:  
  
-   Для создания `CDaoRecordset` объекта  
  
-   Для вызова объекта **Execute** функции-члена непосредственное выполнение запроса или запроса к серверу  
  
 Можно использовать объект querydef для любого типа запроса, включая select, действие, перекрестного, удаление, обновление, добавление, создание таблицы, определение данных, к серверу SQL, объединения и массовые запросы. Тип запроса определяется содержимое инструкции SQL, необходимо указать. Сведения о типах запросов см. в разделе **Execute** и [GetType](#gettype) функции-члены. Наборы записей обычно используются для возврата строки запросов, обычно используемых в **ВЫБЕРИТЕ... ИЗ** ключевые слова. **Выполнение** чаще всего используется для массовых операций. Дополнительные сведения см. в разделе [Execute](#execute) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>Querydefs и наборы данных  
 Использовать для создания объекта querydef `CDaoRecordset` объекта, обычно создается или открывается querydef, как описано выше. Затем создайте объект набора записей, передать указатель на объект querydef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Передаваемые querydef должно быть в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Querydef нельзя использовать для создания набора записей (наиболее распространенное использование для querydef), если он находится в открытом состоянии. Поместите querydef в открытом состоянии с помощью вызова **откройте** или **создать**.  
  
## <a name="external-databases"></a>Внешние базы данных  
 Объекты QueryDef являются предпочтительным способом для использования собственного диалект SQL из механизма внешней базы данных. Например можно создать запрос Transact SQL (как в Microsoft SQL Server) и сохраните его в объект querydef. Если необходимо использовать SQL-запрос, не зависит от базы данных Microsoft Jet, необходимо указать строку подключения, указывающую на внешний источник данных. Запросы с допустимых строк соединения обхода ядро базы данных и передает запрос непосредственно на сервере внешней базы данных для использования.  
  
> [!TIP]
>  Предпочтительным способом для работы с таблицами ODBC является присоедините их к Microsoft Jet (. База данных MDB).  
  
 Дополнительные сведения см. в разделах «QueryDef объект», «QueryDefs-коллекция» и «CdbDatabase объект» в пакете SDK DAO.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="append"></a>CDaoQueryDef::Append  
 Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта querydef.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Примечания  
 **Добавление** сохраняет querydef в базе данных путем добавления объекта к коллекции QueryDefs базы данных. Можно использовать как временный объект querydef без добавления его, но если требуется его сохранить, необходимо вызвать **Append**.  
  
 При попытке добавить объект временного querydef MFC создает исключение типа [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 Вызов этой функции-члена для определения, можно ли изменить querydef — например, изменить его имя или строку SQL.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вы имеете право изменять querydef; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вы можете изменить querydef, если:  
  
-   Он основан не на базу данных, которая открыта только для чтения.  
  
-   Иметь разрешения на обновление базы данных.  
  
     Это зависит от того, реализуется ли функции безопасности. MFC не предоставляет поддержку для безопасности; необходимо реализовать его самостоятельно вызов DAO напрямую или с помощью Microsoft Access. В разделе «Разрешения свойство» в справке DAO.  
  
##  <a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 Создает **CDaoQueryDef** объекта.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Параметры  
 `pDatabase`  
 Указатель на открытый [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Объект может представлять существующего querydef хранится в коллекции QueryDefs базы данных, запроса должны храниться в коллекции или временный запрос, не должен быть сохранен. Следующий шаг зависит от типа querydef:  
  
-   Если объект представляет существующего querydef, вызывающие этот объект [откройте](#open) функции-члена для его инициализации.  
  
-   Если объект представляет новый querydef должен быть сохранен, вызывающие этот объект [создать](#create) функции-члена. Объект добавляется в коллекцию QueryDefs базы данных. Затем вызовите `CDaoQueryDef` функции-члены, чтобы задать атрибуты объекта. Наконец, вызовите [Append](#append).  
  
-   Если объект представляет временной querydef (не сохраняется в базе данных), вызовите **создать**, передача пустой строки для имени запроса. После вызова метода **создать**, инициализировать querydef напрямую, задав его атрибуты. Не следует вызывать **Append**.  
  
 Чтобы задать атрибуты querydef, можно использовать [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), и [SetReturnsRecords](#setreturnsrecords) функции-члены.  
  
 После завершения работы с объектом querydef, вызвать его [закрыть](#close) функции-члена. Если указатель querydef, используйте **удаление** оператор для уничтожения объекта C++.  
  
##  <a name="close"></a>CDaoQueryDef::Close  
 После завершения использования объекта querydef, вызовите эту функцию-член.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Закрытие querydef освобождает базового объекта DAO, но не удаляет сохраненный объект querydef DAO или C++ `CDaoQueryDef` объекта. Это не является таким же, как [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), которая удаляет querydef из коллекции QueryDefs базы данных в DAO (если не временный querydef).  
  
##  <a name="create"></a>CDaoQueryDef::Create  
 Вызовите эту функцию-член для создания новых сохраненный запрос или новый временный запрос.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Уникальное имя запроса, сохраненного в базе данных. Дополнительные сведения о строке см. в разделе «Метод CreateQueryDef» в справке DAO. Чтобы принять значение по умолчанию — пустая строка, создается временный querydef. Такой запрос не сохраняется в QueryDefs-коллекция.  
  
 `lpszSQL`  
 Строка SQL, определяющую запрос. Чтобы принять значение по умолчанию **NULL**, позднее необходимо вызвать [SetSQL](#setsql) задать строку. Пока запрос не определено. Тем не менее, можно использовать запрос не определено для открытия набора записей; Дополнительные сведения см. Перед добавлением в коллекцию QueryDefs querydef, должны быть определены инструкции SQL.  
  
### <a name="remarks"></a>Примечания  
 Если передать имя в `lpszName`, затем можно вызвать [Append](#append) сохранить querydef в базе данных QueryDefs-коллекция. В противном случае — объект имеет временный querydef и не сохраняются. В любом случае querydef находится в открытом состоянии, и его можно использовать либо для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта или вызвать querydef [Execute](#execute) функции-члена.  
  
 Если не указать инструкцию SQL в `lpszSQL`, не может выполнить запрос с **Execute** , но его можно использовать для создания набора записей. В этом случае MFC использует инструкции SQL набора записей по умолчанию.  
  
##  <a name="execute"></a>CDaoQueryDef::Execute  
 Вызовите эту функцию-член для выполнения запроса, определенный объектом querydef.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Параметры  
 `nOptions`  
 Целое число, определяющий параметры запроса. Дополнительные сведения см. в разделе «Выполнить метод» в справке DAO. Можно использовать оператор побитового или ( **|**) для объединения следующие константы для этого аргумента:  
  
- **dbDenyWrite** запретить разрешение на запись для других пользователей.  
  
- **dbInconsistent** несогласованных обновлений.  
  
- **dbConsistent** согласованности обновлений.  
  
- **dbSQLPassThrough** к серверу SQL. Приводит к можно передать в базе данных ODBC для обработки инструкции SQL.  
  
- **dbFailOnError** значение по умолчанию. Откат обновления при возникновении ошибки и ошибки отчета пользователю.  
  
- **dbSeeChanges** формирования ошибки во время выполнения, если другой пользователь изменяет редактировании данных.  
  
> [!NOTE]
>  Объяснение терминов «несогласованные» и «согласованность», см. в разделе «Выполнить метод» в справке DAO.  
  
### <a name="remarks"></a>Примечания  
 QueryDef объекты, используемые для выполнения таким образом может представлять только один из следующих типов запросов:  
  
-   Запросы  
  
-   Запросы к серверу SQL  
  
 **Выполнение** не работает для запросов, возвращающих записей, например запросы select. **Выполнение** часто используемые для запросов массовой операции, такие как **обновление**, **вставки**, или **SELECT INTO**, или для операций языка DDL для определения данных.  
  
> [!TIP]
>  Предпочтительный способ работы с источниками данных ODBC — присоединение таблиц Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ внешних баз данных с DAO», справки DAO.  
  
 Вызов [GetRecordsAffected](#getrecordsaffected) функции-члена объекта querydef, чтобы определить количество строк, затронутых последней **Execute** вызова. Например `GetRecordsAffected` возвращает сведения о количестве записей удалены, обновляемых или вставляемых при выполнении запроса. Возвращенное число не будет отражать изменения в связанных таблицах, когда cascade обновляет или удаляет вступают в силу.  
  
 Если вы оставите и **dbInconsistent** и **dbConsistent** или если ни один, результатом является значение по умолчанию **dbInconsistent**.  
  
 **Выполнение** не возвращает набор записей. С помощью **Execute** на запрос, который выбирает записи вызывает MFC для создания исключения типа [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="getconnect"></a>CDaoQueryDef::GetConnect  
 Вызовите эту функцию-член для получения строки подключения, связанный с источником данных querydef.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) содержащей строку подключения для querydef.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется только с источниками данных ODBC и некоторые драйверы ISAM. Он не используется с Microsoft Jet (. Баз данных MDB); в этом случае `GetConnect` возвращает пустую строку. Дополнительные сведения см. в разделе [SetConnect](#setconnect).  
  
> [!TIP]
>  Предпочтительным способом для работы с таблицами ODBC является подключите их к. База данных MDB. Дополнительные сведения см. в разделе «Доступ внешних баз данных с DAO», справки DAO.  
  
 Дополнительные сведения о строках соединения см. в разделе «Свойства подключения», в справке DAO.  
  
##  <a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 Вызовите эту функцию-член для получения дату создания объекта querydef.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время создания querydef.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
##  <a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 Вызов этой функции-члена для получения объекта querydef дату последнего обновления, когда свойства были изменены, например его имя, ее строка SQL или ее строка подключения.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время последнего обновления querydef.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
##  <a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 Вызовите эту функцию-член для получения числа полей в запросе.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей, определенных в запросе.  
  
### <a name="remarks"></a>Примечания  
 `GetFieldCount`полезно для перебора всех полей в querydef. Для этой цели используйте `GetFieldCount` в сочетании с [GetFieldInfo](#getfieldinfo).  
  
##  <a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo  
 Вызовите эту функцию-член для получения различных типов сведений о поле, определенное в querydef.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс в коллекции Fields querydef, для поиска по индексу нужного поля.  
  
 `fieldinfo`  
 Ссылку на `CDaoFieldInfo` объекта, который возвращает запрошенные данные.  
  
 `dwInfoOptions`  
 Параметры, определяющие, какие поля для извлечения. Ниже перечислены доступные параметры и что они могут вызывать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, тип, размер, атрибуты  
  
- `AFX_DAO_SECONDARY_INFO`А также сведения об основном: порядковый номер, необходимые, разрешить нулевой длины, исходное поле, внешнего имени исходной таблицы, порядок сортировки  
  
- `AFX_DAO_ALL_INFO`Основной и дополнительной информации плюс: значение по умолчанию текст для проверки, правила проверки  
  
 `lpszName`  
 Строка, содержащая имя нужного поля для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 Описание сведений, возвращаемых в `fieldinfo`, в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе `dwInfoOptions` выше. Если запрос один уровень информации, вы получаете все предыдущие уровни также сведения.  
  
##  <a name="getname"></a>CDaoQueryDef::GetName  
 Вызовите эту функцию-член для извлечения имени запрос, представленный querydef.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя запроса.  
  
### <a name="remarks"></a>Примечания  
 Имена QueryDef, уникальные имена определенных пользователем. Дополнительные сведения об именах querydef см. в разделе «Свойства Name» в справке DAO.  
  
##  <a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 Вызов этой функции-члена для получения за выделенное время, по истечении времени ожидания запроса к источнику данных ODBC.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число секунд до истечения запроса истекает.  
  
### <a name="remarks"></a>Примечания  
 Сведения о этот промежуток времени см. в разделе «Время ожидания ODBC свойство» в справке DAO.  
  
> [!TIP]
>  Предпочтительным способом для работы с таблицами ODBC является присоедините их к Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ внешних баз данных с DAO», справки DAO.  
  
##  <a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 Вызовите эту функцию-член для получения числа параметров в сохраненный запрос.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число параметров, определенных в запросе.  
  
### <a name="remarks"></a>Примечания  
 `GetParameterCount`полезно для перебора всех параметров в querydef. Для этой цели используйте `GetParameterCount` в сочетании с [GetParameterInfo](#getparameterinfo).  
  
 Дополнительные сведения см. в разделах «Объект параметра», «Коллекции параметров» и «параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo  
 Вызовите эту функцию-член для получения сведений о параметрах, определенных в querydef.  
  
```  
void GetParameterInfo(
    int nIndex,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetParameterInfo(
    LPCTSTR lpszName,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс нужный параметр в коллекции параметров querydef, для поиска по индексу.  
  
 `paraminfo`  
 Ссылку на [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) объекта, который возвращает запрошенные данные.  
  
 `dwInfoOptions`  
 Параметры, определяющие, какие извлекаемого параметра. А также то, что вызывает функцию для возврата доступен параметр указанный здесь:  
  
- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя типа  
  
 `lpszName`  
 Строка, содержащая имя требуемого параметра, для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 Описание сведений, возвращаемых в `paraminfo`, в разделе [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе `dwInfoOptions` выше.  
  
 Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getparamvalue"></a>CDaoQueryDef::GetParamValue  
 Вызовите эту функцию-член для получения текущего значения заданного параметра, хранятся в коллекции параметров querydef.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Имя параметра, значение которого требуется, для поиска по имени.  
  
 `nIndex`  
 Отсчитываемый от нуля индекс параметра в коллекции параметров querydef, для поиска по индексу. Можно получить это значение с помощью вызовов [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение параметра.  
  
### <a name="remarks"></a>Примечания  
 Параметр доступны по имени или по его порядковому номеру в коллекции.  
  
 Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 Вызов этой функции-члена для определения, сколько записей были затронуты при последнем вызове [Execute](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество обработанных записей.  
  
### <a name="remarks"></a>Примечания  
 Возвращенное число не будет отражать изменения в связанных таблицах, когда cascade обновляет или удаляет вступают в силу.  
  
 Дополнительные сведения см. в разделе «Свойство RecordsAffected» в справке DAO.  
  
##  <a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 Вызовите эту функцию-член для определения ли querydef основан на запросе, который возвращает записи.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если querydef основан на запросе, который возвращает записи; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется только для запросов к серверу. Дополнительные сведения о запросах SQL см. в разделе [Execute](#execute) функции-члена. Дополнительные сведения о работе с запросами к серверу SQL см. в разделе [SetReturnsRecords](#setreturnsrecords) функции-члена.  
  
 Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.  
  
##  <a name="getsql"></a>CDaoQueryDef::GetSQL  
 Вызов этой функции-члена для получения инструкции SQL, определяющей запрос, лежащие в основе querydef.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Инструкция SQL, определяющей запрос, лежащие в основе querydef.  
  
### <a name="remarks"></a>Примечания  
 Затем будет, вероятно, проанализировать строку для ключевых слов, имена таблиц и т. д.  
  
 Дополнительные сведения см. в разделах «Свойство SQL», «Сравнение Microsoft Jet базы данных ядро SQL и ANSI SQL» и «Запрос базы данных с SQL в код» в справке DAO.  
  
##  <a name="gettype"></a>CDaoQueryDef::GetType  
 Вызов этой функции-члена для определения типа запроса querydef.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип запроса, определяются querydef. Значения см.  
  
### <a name="remarks"></a>Примечания  
 Тип запроса задается то, что указано в строке querydef SQL при создании querydef или вызвать существующего querydef [SetSQL](#setsql) функции-члена. Тип запроса возвращает эта функция может принимать одно из следующих значений:  
  
- **dbQSelect** выберите  
  
- **dbQAction** действия  
  
- **dbQCrosstab** перекрестный  
  
- **dbQDelete** удаления  
  
- **dbQUpdate** обновления  
  
- **dbQAppend** Append  
  
- **dbQMakeTable** создание таблицы  
  
- **dbQDDL** определение данных  
  
- **dbQSQLPassThrough** к серверу  
  
- **dbQSetOperation** объединения  
  
- **dbQSPTBulk** с **dbQSQLPassThrough** указать запрос, который возвращает записи.  
  
> [!NOTE]
>  Создание запроса к серверу, не задавайте **dbSQLPassThrough** константой. Он задается автоматически ядром базы данных Microsoft Jet при создании объекта querydef и задать строку подключения.  
  
 Сведения о строках SQL см. в разделе [GetSQL](#getsql). Сведения о типах запросов см. в разделе [Execute](#execute).  
  
##  <a name="isopen"></a>CDaoQueryDef::IsOpen  
 Вызов этой функции-члена для определения ли `CDaoQueryDef` объект открыт в данный момент.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CDaoQueryDef` объект, открытые в настоящий момент; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Прежде чем использовать его для вызова querydef должны находиться в открытом состоянии [Execute](#execute) или создать [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта. Перевод querydef в открытом состоянии вызова либо [создать](#create) (для новых querydef) или [откройте](#open) (для существующего querydef).  
  
##  <a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) связанный с объектом querydef.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот указатель для прямого доступа к базе данных — например, для получения ссылки на другие querydef или набора записей объекты в коллекции базы данных.  
  
##  <a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 Содержит указатель на интерфейс OLE для базового объекта querydef DAO.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель обеспечивает полноту и согласованность с другими классами. Тем не менее так как MFC инкапсулирует вместо полностью DAO querydefs, вряд ли можно она нужна. Если вы используете его, делать это осторожно – в частности, не изменяйте значение указателя, если известно, что делает.  
  
##  <a name="open"></a>CDaoQueryDef::Open  
 Вызовите эту функцию-член для открытия querydef, сохраненные в базе данных QueryDefs-коллекция.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Строка, содержащая имя сохраненного querydef, чтобы открыть. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 После открытия querydef можно вызвать его [Execute](#execute) функции-члена или используйте querydef для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.  
  
##  <a name="setconnect"></a>CDaoQueryDef::SetConnect  
 Вызовите эту функцию-член для задания строки подключения объекта querydef.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszConnect`  
 Строка, содержащая строку подключения для связанных [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Строка подключения используется для передачи дополнительных сведений к ODBC и некоторые драйверы ISAM, при необходимости. Он не используется для Microsoft Jet (. Базы данных MDB).  
  
> [!TIP]
>  Предпочтительным способом для работы с таблицами ODBC является подключите их к. База данных MDB.  
  
 Перед выполнением querydef, представляющий запрос к серверу SQL к источнику данных ODBC, задать строку соединения с `SetConnect` и вызвать [SetReturnsRecords](#setreturnsrecords) для указания, является ли запрос возвращает записи.  
  
 Дополнительные сведения о структуре и примеры компоненты строки соединения строки подключения см. в разделе «Свойства подключения», в справке DAO.  
  
##  <a name="setname"></a>CDaoQueryDef::SetName  
 Вызовите эту функцию-член, если вы хотите изменить имя querydef, который не является временным.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Строка, содержащая новое имя для запроса nontemporary в связанном [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 QueryDef имена являются именами уникальный, определяемый пользователем. Можно вызвать `SetName` перед querydef объект добавляется в коллекцию QueryDefs.  
  
##  <a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 Вызовите эту функцию-член, чтобы ограничить время до истечения срока запроса к источнику данных ODBC.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Параметры  
 *nODBCTimeout*  
 Число секунд до истечения запроса истекает.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член позволяет переопределить значение по умолчанию в секундах в последующих операциях в подключенный источник данных «время ожидания». Операция может времени из-за проблем доступа к сети, время обработки запроса слишком и т. д. Вызов `SetODBCTimeout` до выполнения запроса с этой querydef, если требуется изменить значение времени ожидания запроса. (Как ODBC использует подключения, значение времени ожидания является одинаковым для всех клиентов в том же соединении.)  
  
 Значение по умолчанию для времени ожидания запросов составляет 60 секунд.  
  
##  <a name="setparamvalue"></a>CDaoQueryDef::SetParamValue  
 Вызовите эту функцию-член для задания значения параметра в querydef во время выполнения.  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Имя параметра, значение которого требуется задать.  
  
 `varValue`  
 Задаваемое значение; см. заметки.  
  
 `nIndex`  
 Порядковый номер параметра в коллекции параметров querydef. Можно получить это значение с помощью вызовов [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).  
  
### <a name="remarks"></a>Примечания  
 Параметр должна быть уже установлена как часть строки querydef SQL. Параметр доступны по имени или по его порядковому номеру в коллекции.  
  
 Укажите значение, которое задается как `COleVariant` объект. Сведения о настройке нужное значение и тип в вашей `COleVariant` объекта см. в разделе класса [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 Вызовите эту функцию-член как часть процесса настройки запроса к серверу к внешней базе данных.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Параметры  
 *bReturnsRecords*  
 Передайте **TRUE** Если запрос на внешней базы данных возвращает записи; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 В этом случае необходимо создать querydef и задать его свойства с помощью других `CDaoQueryDef` функции-члены. Описание внешних баз данных см. в разделе [SetConnect](#setconnect).  
  
##  <a name="setsql"></a>CDaoQueryDef::SetSQL  
 Вызовите эту функцию-член для задания SQL, который выполняет querydef.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSQL`  
 Строка, содержащая полную инструкцию SQL, подходящие для выполнения. Синтаксис этой строки зависит от СУБД, используемой для запроса. Описание синтаксиса, используемого в ядре базы данных Microsoft Jet см. в разделе «Создание SQL инструкций в код» в справке DAO.  
  
### <a name="remarks"></a>Примечания  
 Типичное использование `SetSQL` настраивается объекта querydef для использования в запросе к серверу SQL. (Синтаксис запросов к серверу на целевой СУБД, см. в документации по используемой СУБД.)  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-класс](../../mfc/reference/cdaorecordset-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)   
 [Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [Класс CDaoException](../../mfc/reference/cdaoexception-class.md)

