---
title: Класс CDaoQueryDef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3af520de7e92a887f9a49fea7262d7f51b74082
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954638"
---
# <a name="cdaoquerydef-class"></a>Класс CDaoQueryDef
Представляет определение запроса или QueryDef, как правило, сохраненный в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Создает объект `CDaoQueryDef`. Затем вызовите метод `Open` или `Create`, в зависимости от потребностей.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|Добавляет querydef QueryDefs-коллекция базы данных как сохраненный запрос.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если запрос можно обновить базу данных.|  
|[CDaoQueryDef::Close](#close)|Закрытие объекта querydef. Удаляет этот объект C++ после завершения работы с его.|  
|[CDaoQueryDef::Create](#create)|Создает объект базового querydef DAO. Использовать в качестве временного запроса или вызова querydef `Append` сохранить его в базе данных.|  
|[CDaoQueryDef::Execute](#execute)|Выполняет запрос, определенными объектом querydef.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Возвращает строку подключения, связанную с querydef. Строка подключения определяет источник данных. (Для SQL передаваемых запросов только; в противном случае — пустая строка.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Возвращает дату создания сохраненного запроса.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату последнего обновления сохраненного запроса.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Возвращает число полей, определенных querydef.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Возвращает сведения о указанного поля, определенные в запросе.|  
|[CDaoQueryDef::GetName](#getname)|Возвращает имя querydef.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Возвращает значение времени ожидания, используемый ODBC (ODBC запроса) при выполнении querydef. Это определяет, как долго для завершения действия запроса.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Возвращает число параметров, определенных для запроса.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Возвращает сведения о указанного параметра в запрос.|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Возвращает значение указанного параметра в запрос.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Возвращает количество записей, затронутых запросом.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Возвращает ненулевое значение, если запрос определяется querydef возвращает записи.|  
|[CDaoQueryDef::GetSQL](#getsql)|Возвращает строку SQL, определяющая запрос, определяется querydef.|  
|[CDaoQueryDef::GetType](#gettype)|Возвращает тип запроса: удаление, обновление, добавление, создание таблицы и т. д.|  
|[CDaoQueryDef::IsOpen](#isopen)|Возвращает ненулевое значение, если querydef открыт и могут быть выполнены.|  
|[CDaoQueryDef::Open](#open)|Открывает существующий querydef, хранящихся в коллекции QueryDefs базы данных.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Задает строку подключения для запроса к серверу на источник данных ODBC.|  
|[CDaoQueryDef::SetName](#setname)|Задает имя сохраненного запроса, заменив имя используется при создании querydef.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Задает значение времени ожидания, используемый ODBC (ODBC запроса) при выполнении querydef.|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Задает значение указанного параметра в запрос.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Определяет, возвращает ли querydef записей. Задав этому атрибуту значение **TRUE** допустимо только для запросов к серверу.|  
|[CDaoQueryDef::SetSQL](#setsql)|Задает строку SQL, определяющая запрос, определяется querydef.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Указатель на интерфейс OLE для базового объекта querydef DAO.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Указатель на `CDaoDatabase` объект, с которым связан querydef. Querydef может быть сохранен в базе данных, или нет.|  
  
## <a name="remarks"></a>Примечания  
 Querydef представляет собой объект данных доступа, который содержит инструкцию SQL, описывающую запрос и его свойства, такие как «Дата создания» и «Время ожидания ODBC». Можно также создать временные querydef объекты без сохранения, но он является удобным, — и более эффективный способ — для сохранения обычно повторно использовать запросы в базе данных. Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) сохраняет в коллекцию с именем QueryDefs, содержащую коллекцию его сохраненного querydefs.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC; классы на основе DAO доступны данные, включая через драйверы ODBC, через свои собственные компонента database engine. Классы на основе DAO также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, без необходимости непосредственный вызов DAO.  
  
## <a name="usage"></a>Использование  
 С помощью querydef объектов либо для работы с существующим сохраненный запрос или создайте новый запрос или временный запрос сохранен:  
  
1.  Во всех случаях сначала создать `CDaoQueryDef` объекта, предоставляющего указатель [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта, которому принадлежит запрос.  
  
2.  Затем выполните следующую команду, в зависимости от того, какие действия следует:  
  
    -   Чтобы использовать существующий сохраненный запрос, вызвать метод объекта querydef [откройте](#open) функция-член, указав имя сохраненного запроса.  
  
    -   Чтобы создать новый сохраненный запрос, вызовите объекта querydef [создать](#create) функция-член, указав имя запроса. Затем вызовите [Append](#append) сохранить запрос путем добавления его к QueryDefs-коллекция базы данных. `Create` Помещает querydef в открытом состоянии, поэтому после вызова `Create` не вызывается `Open`.  
  
    -   Чтобы создать временный querydef, вызовите `Create`. Необходимо передайте пустую строку для имени запроса. Не вызывайте `Append`.  
  
 После завершения работы с объектом querydef, вызовите его [закрыть](#close) члена функции; затем удалите объект querydef.  
  
> [!TIP]
>  Для их создания и сохранения их в базу данных с помощью Microsoft Access является самым простым способом создания сохраненных запросов. Затем можно открыть и использовать их в коде MFC.  
  
## <a name="purposes"></a>В целях  
 Можно использовать объект querydef для любого из следующих целей:  
  
-   Для создания `CDaoRecordset` объекта  
  
-   Для вызова объекта `Execute` функции-члена для непосредственное выполнение запроса или запроса к серверу  
  
 Можно использовать объект querydef для любого типа запроса, включая select, действие, перекрестный, delete, update, добавление, создание таблицы, определение данных, к серверу SQL, union и массовые запросы. Тип запроса определяется содержимое, указываемое инструкции SQL. Сведения о типах запросов см. в разделе `Execute` и [GetType](#gettype) функции-члены. Наборы записей обычно используются для возвращения строк запросов, обычно используемых в **ВЫБЕРИТЕ... ИЗ** ключевые слова. `Execute` Чаще всего используется для массовых операций. Дополнительные сведения см. в разделе [Execute](#execute) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>Querydefs и наборы данных  
 Использование для создания объекта querydef `CDaoRecordset` объект обычно создается или открывается querydef, как описано выше. Затем создайте объект набора записей, указателю на объект querydef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Передаваемые querydef должен быть в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Querydef нельзя использовать для создания набора записей (чаще всего используют для querydef), если он находится в открытом состоянии. Перевести querydef в открытом состоянии с помощью вызова `Open` или `Create`.  
  
## <a name="external-databases"></a>Внешние базы данных  
 Объекты QueryDef являются предпочтительным способом для использования собственного разновидности языка SQL ядра внешней базы данных. Например можно создать запрос Transact SQL (как указано в Microsoft SQL Server) и сохраните его в объект querydef. При необходимости использовать SQL-запрос, не зависит от базы данных Microsoft Jet, необходимо указать строку соединения, указывающий на внешнем источнике данных. Запросы с допустимых строк соединения обхода ядро базы данных и передает запрос непосредственно на сервере внешней базы данных для использования.  
  
> [!TIP]
>  Предпочтительный способ работы с таблицами ODBC — присоединение их Microsoft Jet (. База данных MDB).  
  
 Дополнительные сведения см. в разделах «QueryDef объект», «QueryDefs-коллекция» и «CdbDatabase объект» в пакете SDK DAO.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="append"></a>  CDaoQueryDef::Append  
 Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта querydef.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Примечания  
 `Append` сохраняет querydef в базе данных путем добавления объекта в коллекцию QueryDefs базы данных. Можно использовать как временный объект querydef без добавления ее, но если нужно сохранить, необходимо вызвать `Append`.  
  
 При попытке добавить объект временные querydef MFC вызывает исключение типа [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate  
 Вызовите эту функцию-член для определения того, можно ли изменить querydef — например, изменение его имя или строка SQL.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вы имеете право изменять querydef; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы изменить querydef:  
  
-   Он основан не на базе данных, открывается только для чтения.  
  
-   Имеются разрешения на обновление базы данных.  
  
     Это зависит от того, реализуется ли функции безопасности. MFC не предоставляет поддержку для безопасности; необходимо реализовать ее самостоятельно, вызов DAO напрямую или с помощью Microsoft Access. См. в разделе «Разрешения свойство» в справке DAO.  
  
##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef  
 Создает объект `CDaoQueryDef`.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Параметры  
 *pDatabase*  
 Указатель на открытый [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Объект может представлять существующего querydef, хранящихся в QueryDefs-коллекция базы данных, запроса для сохранения в коллекцию или временный запрос, не должны сохраняться. Следующий шаг зависит от типа querydef:  
  
-   Если объект представляет существующего querydef, вызывающие этот объект [откройте](#open) функции-члена для его инициализации.  
  
-   Если объект представляет новый querydef должен быть сохранен, вызывающие этот объект [создать](#create) функции-члена. Это добавляет объект QueryDefs-коллекция базы данных. Затем вызовите `CDaoQueryDef` функции-члены для задания атрибутов объекта. Наконец, вызовите [Append](#append).  
  
-   Если объект представляет временной querydef (не должен быть сохранен в базе данных), вызовите `Create`, передать пустую строку для имени запроса. После вызова метода `Create`, инициализировать querydef напрямую, установив его атрибуты. Не вызывайте `Append`.  
  
 Чтобы задать атрибуты querydef, можно использовать [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)и [SetReturnsRecords](#setreturnsrecords) функции-члены.  
  
 После завершения работы с объектом querydef, вызовите его [закрыть](#close) функции-члена. Если имеется указатель на querydef использовать **удалить** оператор для уничтожения объекта C++.  
  
##  <a name="close"></a>  CDaoQueryDef::Close  
 После завершения работы с объектом querydef, вызовите эту функцию-член.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Закрытие querydef освобождает объект базового DAO, но не удаляет сохраненный объект querydef DAO или C++ `CDaoQueryDef` объекта. Это не то же, что [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), которая удаляет querydef из QueryDefs-коллекция базы данных в DAO (если не временный querydef).  
  
##  <a name="create"></a>  CDaoQueryDef::Create  
 Вызовите эту функцию-член для создания нового сохраненный запрос или новый временный запрос.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Уникальное имя запроса, сохраненного в базе данных. Дополнительные сведения о строке см. в разделе «Метод CreateQueryDef» в справке DAO. Если принять значение по умолчанию — пустая строка, создается временный querydef. Такой запрос не сохраняются в QueryDefs-коллекция.  
  
 *lpszSQL*  
 Строка SQL, определяющей запрос. Чтобы принять значение по умолчанию **NULL**, более поздней версии, необходимо вызвать метод [SetSQL](#setsql) для настройки строки. А пока запрос не определено. Однако, не определено запроса можно использовать для открытия набора записей; Дополнительные сведения см. заметки. Инструкции SQL должен быть определен перед добавлением в коллекцию QueryDefs querydef.  
  
### <a name="remarks"></a>Примечания  
 Если передать имя в *lpszName*, затем можно вызвать [Append](#append) для сохранения в базе данных QueryDefs-коллекция querydef. В противном случае объект имеет временный querydef и не сохраняется. В любом случае querydef находится в открытом состоянии и либо его можно использовать для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта или вызвать querydef [Execute](#execute) функции-члена.  
  
 Если не указать инструкцию SQL в *lpszSQL*, не может выполнить запрос с `Execute` , но его можно использовать для создания набора записей. В этом случае MFC использует инструкции SQL набора записей по умолчанию.  
  
##  <a name="execute"></a>  CDaoQueryDef::Execute  
 Вызовите эту функцию-член для выполнения запроса, определенными объектом querydef.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Параметры  
 *nOptions*  
 Целое число, определяющий характеристики запроса. Дополнительные сведения см. в разделе «Выполнить метод» в справке DAO. Можно использовать оператор побитового или ( **&#124;**) для объединения следующих констант для данного аргумента:  
  
- **dbDenyWrite** запретить разрешение на запись для других пользователей.  
  
- **dbInconsistent** несогласованных обновлений.  
  
- **dbConsistent** согласованности обновлений.  
  
- **dbSQLPassThrough** к серверу SQL. Вызывает инструкцию SQL для передачи базы данных ODBC для обработки.  
  
- **dbFailOnError** значение по умолчанию. Откат обновления при возникновении ошибки и ошибки отчета пользователю.  
  
- **dbSeeChanges** формирования ошибки во время выполнения, если другой пользователь изменение данных, вы изменяете.  
  
> [!NOTE]
>  Объяснение термины «несогласованные» и «согласованного», см. в разделе «Выполнить метод» в справке DAO.  
  
### <a name="remarks"></a>Примечания  
 QueryDef объекты, используемые для выполнения, таким образом может представлять только один из следующих типов запросов:  
  
-   Запросов на изменение  
  
-   Запросы к серверу SQL  
  
 `Execute` не работает для запросов, возвращающих записей, например запросы select. `Execute` обычно используется для запросов массовой операции, такие как **обновление**, **вставить**, или **SELECT INTO**, или для операций языка DDL для определения данных.  
  
> [!TIP]
>  Предпочтительный способ работы с источниками данных ODBC — присоединение таблиц Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», справки DAO.  
  
 Вызовите [GetRecordsAffected](#getrecordsaffected) функции-члена объекта querydef, чтобы определить количество строк, затронутых последней `Execute` вызова. Например `GetRecordsAffected` возвращает сведения о количестве записей удален, обновления или вставки при выполнении запроса. Число, возвращаемое не будет отражать изменения в связанных таблицах, когда cascade, обновляет или удаляет вступают в силу.  
  
 Если одновременно включать **dbInconsistent** и **dbConsistent** или если ни один, результатом является значение по умолчанию **dbInconsistent**.  
  
 `Execute` Возвращает набор записей. С помощью `Execute` на запрос, который выбирает записи вызывает MFC для создания исключения типа [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect  
 Вызовите эту функцию-член для получения строки подключения, связанный с источником данных querydef.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) содержится строка подключения для querydef.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется только с источниками данных ODBC и некоторые драйверы ISAM. Он не используется с Microsoft Jet (. Баз данных MDB). в этом случае `GetConnect` возвращает пустую строку. Дополнительные сведения см. в разделе [SetConnect](#setconnect).  
  
> [!TIP]
>  Подключите их к является предпочтительным способом для работы с таблицами ODBC. База данных MDB. Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», справки DAO.  
  
 Дополнительные сведения о строках соединения см. в разделе «Свойства подключения», справки DAO.  
  
##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated  
 Вызовите эту функцию-член для получения дату создания объекта querydef.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время создания querydef.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated  
 Вызов этой функции-члена для получения объекта querydef Дата последнего обновления, при любой из его свойств были изменены, например его имя, его строка SQL или строке соединения.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время последнего обновления querydef.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount  
 Вызовите эту функцию-член для извлечения номера поля в запросе.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей, определенных в запросе.  
  
### <a name="remarks"></a>Примечания  
 `GetFieldCount` полезно для перебора всех полей в querydef. Для этой цели используйте `GetFieldCount` в сочетании с [GetFieldInfo](#getfieldinfo).  
  
##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo  
 Вызовите эту функцию-член для получения различного рода сведения о поле, определенное в querydef.  
  
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
 *nIndex*  
 Отсчитываемый от нуля индекс нужные поля в коллекции полей querydef, для поиска по индексу.  
  
 *FieldInfo*  
 Ссылку на `CDaoFieldInfo` объект, который возвращает запрошенные данные.  
  
 *dwInfoOptions*  
 Параметры, определяющие, какие поля для извлечения. Ниже перечислены доступные параметры и как они вызвать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, тип, размер, атрибуты  
  
- `AFX_DAO_SECONDARY_INFO` А также сведения о первичном: порядковый номер, необходимые, разрешить нулевой длины, исходное поле, внешнего имени, исходной таблицы, порядок сортировки  
  
- `AFX_DAO_ALL_INFO` Основной и дополнительной информации плюс: значение по умолчанию текст проверки правила проверки  
  
 *lpszName*  
 Строка, содержащая имя нужного поля для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 Описание сведений, возвращаемых в *fieldinfo*, в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе *dwInfoOptions* выше. Если пользователь запрашивает один уровень данных, вы получаете все предыдущие уровни подобных сведений.  
  
##  <a name="getname"></a>  CDaoQueryDef::GetName  
 Вызовите эту функцию-член для извлечения имени запрос, представленный querydef.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя запроса.  
  
### <a name="remarks"></a>Примечания  
 QueryDef имена, уникальные имена, определяемые пользователем. Дополнительные сведения об именах querydef см. в разделе «Имя свойства» в справке DAO.  
  
##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout  
 Вызовите эту функцию-член для получения за выделенное время по истечении времени ожидания запроса к источнику данных ODBC.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество секунд до запрос времени ожидания.  
  
### <a name="remarks"></a>Примечания  
 Сведения о этот промежуток времени см. в разделе «Время ожидания ODBC свойство» в справке DAO.  
  
> [!TIP]
>  Предпочтительный способ работы с таблицами ODBC — присоединение их Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», справки DAO.  
  
##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount  
 Вызовите эту функцию-член для извлечения номера параметров в сохраненный запрос.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число параметров, определенных в запросе.  
  
### <a name="remarks"></a>Примечания  
 `GetParameterCount` полезно для перебора всех параметров в querydef. Для этой цели используйте `GetParameterCount` в сочетании с [GetParameterInfo](#getparameterinfo).  
  
 Дополнительные сведения см. в разделах «Параметр объект», «Коллекции параметров» и «параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo  
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
 *nIndex*  
 Отсчитываемый от нуля индекс нужный параметр в коллекции параметров querydef, для поиска по индексу.  
  
 *подчеркивающие*  
 Ссылку на [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) объект, который возвращает запрошенные данные.  
  
 *dwInfoOptions*  
 Параметры, указывающие, какие сведения о параметре для извлечения. Доступен пункт перечислено ниже, а также что он вызывает функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, тип  
  
 *lpszName*  
 Строка, содержащая имя требуемого параметра, для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 Описание сведений, возвращаемых в *подчеркивающие*, в разделе [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе *dwInfoOptions* выше.  
  
 Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getparamvalue"></a>  CDaoQueryDef::GetParamValue  
 Вызовите эту функцию-член для извлечения текущее значение указанного параметра, сохраненного в коллекции параметров querydef.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Имя параметра, значение которого требуется, чтобы поиск по имени.  
  
 *nIndex*  
 Отсчитываемый от нуля индекс параметра в коллекции параметров querydef, для поиска по индексу. Можно получить это значение с вызовами [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащее значение параметра.  
  
### <a name="remarks"></a>Примечания  
 Параметр доступен по имени или по его порядковому номеру в коллекции.  
  
 Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.  
  
##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected  
 Вызовите эту функцию-член для определения того, сколько записи были затронуты последнем вызове [Execute](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество обработанных записей.  
  
### <a name="remarks"></a>Примечания  
 Число, возвращаемое не будет отражать изменения в связанных таблицах, когда cascade, обновляет или удаляет вступают в силу.  
  
 Дополнительные сведения см. в разделе «Свойство RecordsAffected» в справке DAO.  
  
##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords  
 Вызовите эту функцию-член для определения того, основан ли на запросе, который возвращает записи querydef.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если querydef основан на запросе, который возвращает записи; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется только для запросов к серверу. Дополнительные сведения о запросах SQL см. в разделе [Execute](#execute) функции-члена. Дополнительные сведения о работе с запросами к серверу SQL см. в разделе [SetReturnsRecords](#setreturnsrecords) функции-члена.  
  
 Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.  
  
##  <a name="getsql"></a>  CDaoQueryDef::GetSQL  
 Вызовите эту функцию-член для получения инструкции SQL, определяющей запрос, на котором основан querydef.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Инструкция SQL, определяющей запрос, на котором основан querydef.  
  
### <a name="remarks"></a>Примечания  
 Затем будут, скорее всего, анализировать строку для ключевых слов, имена таблиц и т. д.  
  
 Дополнительные сведения см. в разделах «Свойство SQL», «Сравнение Microsoft Jet базы данных ядра SQL и ANSI SQL» и «Запросов базы данных с SQL в код» в справке DAO.  
  
##  <a name="gettype"></a>  CDaoQueryDef::GetType  
 Вызовите эту функцию-член для определения типа запроса querydef.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип запроса, определенного по querydef. Значения см. примечания.  
  
### <a name="remarks"></a>Примечания  
 Тип запроса задается то, что указано в строке SQL querydef при создании querydef или вызвать существующего querydef [SetSQL](#setsql) функции-члена. Тип запроса возвращает эта функция может принимать одно из следующих значений:  
  
- **dbQSelect** выберите  
  
- **dbQAction** действия  
  
- **dbQCrosstab** перекрестный  
  
- **dbQDelete** удалить  
  
- **dbQUpdate** обновления  
  
- **dbQAppend** Append  
  
- **dbQMakeTable** создание таблицы  
  
- **dbQDDL** определение данных  
  
- **dbQSQLPassThrough** к серверу  
  
- **dbQSetOperation** объединения  
  
- **dbQSPTBulk** с **dbQSQLPassThrough** для указания запроса, который возвращает записи.  
  
> [!NOTE]
>  Создание запроса к серверу, не задано **dbSQLPassThrough** константой. Он задается автоматически ядром базы данных Microsoft Jet при создании объекта querydef и задайте строку подключения.  
  
 Сведения о строках SQL см. в разделе [GetSQL](#getsql). Сведения о типах запросов см. в разделе [Execute](#execute).  
  
##  <a name="isopen"></a>  CDaoQueryDef::IsOpen  
 Вызовите эту функцию-член для определения ли `CDaoQueryDef` объект открыт в данный момент.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CDaoQueryDef` объекта в данный момент открыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Прежде чем использовать его для вызова querydef должно быть в открытом состоянии [Execute](#execute) или создать [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта. Перевод querydef в открытом состоянии вызова либо [создать](#create) (для нового querydef) или [откройте](#open) (для существующего querydef).  
  
##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase  
 Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект, связанный с объектом querydef.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот указатель, если требуется прямой доступ к базе данных — например, для получения ссылки на другие querydef или набора записей объекты в базе данных коллекции.  
  
##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef  
 Содержит указатель на интерфейс OLE для базового объекта querydef DAO.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель обеспечивает полноту и согласованность с другими классами. Тем не менее поскольку вместо полностью MFC инкапсулирует DAO querydefs, их маловероятно, что он нужен. Если вы используете ее, сделать осторожно — в частности, не изменяйте значение указателя Если известно, что делает.  
  
##  <a name="open"></a>  CDaoQueryDef::Open  
 Вызовите эту функцию-член для открытия querydef, хранящихся в базе данных QueryDefs-коллекция.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Строка, содержащая имя сохраненного querydef, чтобы открыть. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 После открытия querydef можно вызвать его [Execute](#execute) функции-члена или используйте для создания querydef [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.  
  
##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect  
 Вызовите эту функцию-член для настройки строки подключения объекта querydef.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszConnect*  
 Строка, содержащая строку подключения для связанных [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Строка подключения используется для передачи дополнительных сведений ODBC и некоторые драйверы ISAM при необходимости. Он не используется для Microsoft Jet (. Базы данных MDB).  
  
> [!TIP]
>  Подключите их к является предпочтительным способом для работы с таблицами ODBC. База данных MDB.  
  
 Перед выполнением querydef, представляющий запрос к серверу SQL к источнику данных ODBC, задайте строку подключения с `SetConnect` и вызвать [SetReturnsRecords](#setreturnsrecords) для указания, является ли запрос возвращает записи.  
  
 Дополнительные сведения о структуре и примеры компоненты строки соединения в строке подключения см. в разделе «Свойства подключения», справки DAO.  
  
##  <a name="setname"></a>  CDaoQueryDef::SetName  
 Вызовите эту функцию-член, если вы хотите изменить имя querydef, который не является временным.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Строка, содержащая новое имя для запроса в связанном nontemporary [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 QueryDef имена являются уникальными, определяемые пользователем имена. Можно вызвать `SetName` перед querydef объект добавляется в коллекцию QueryDefs.  
  
##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout  
 Вызовите эту функцию-член для задания предельного времени до истечения срока запроса к источнику данных ODBC.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Параметры  
 *nODBCTimeout*  
 Количество секунд до запрос времени ожидания.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член позволяет переопределить значение по умолчанию в секундах последующих операциях подключенного источника данных «время ожидания истекло». Время ожидания операции может истекло из-за проблем доступа к сети, время обработки запроса слишком и т. д. Вызовите `SetODBCTimeout` перед выполнением запроса с этой querydef, если вы хотите изменить значение времени ожидания запроса. (Как ODBC используются подключения, значение времени ожидания является одинаковым для всех клиентов в том же соединении.)  
  
 Значение по умолчанию для времени ожидания запросов составляет 60 секунд.  
  
##  <a name="setparamvalue"></a>  CDaoQueryDef::SetParamValue  
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
 *lpszName*  
 Имя параметра, значение которого требуется задать.  
  
 *varValue*  
 Задаваемое значение; см. заметки.  
  
 *nIndex*  
 Порядковый номер параметра в коллекции параметров querydef. Можно получить это значение с вызовами [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).  
  
### <a name="remarks"></a>Примечания  
 Параметр должна быть уже установлена как часть строки querydef SQL. Параметр доступен по имени или по его порядковому номеру в коллекции.  
  
 Укажите значение, которое задается как `COleVariant` объект. Сведения о задании нужное значение и тип в вашей `COleVariant` см. в разделе класса [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords  
 Вызовите эту функцию-член в процессе настройки запроса к серверу к внешней базе данных.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Параметры  
 *bReturnsRecords*  
 Передайте **TRUE** Если на внешней базы данных запрос возвращает записи; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 В этом случае необходимо создать querydef и задать его свойства с помощью других `CDaoQueryDef` функции-члены. Описание внешних баз данных см. в разделе [SetConnect](#setconnect).  
  
##  <a name="setsql"></a>  CDaoQueryDef::SetSQL  
 Вызовите эту функцию-член, чтобы задать инструкцию SQL, которая выполняется querydef.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSQL*  
 Строка, содержащая полную инструкцию SQL, подходящий для выполнения. Синтаксис данной строки зависит от СУБД, используемой для запроса. Описание синтаксиса, используемого в ядре базы данных Microsoft Jet см. в разделе «Построение инструкций в код SQL» справки DAO.  
  
### <a name="remarks"></a>Примечания  
 Типичное применение `SetSQL` является настройка объекта querydef для использования в запросе к серверу SQL. (Синтаксис запросов к серверу в целевой СУБД, см. в документации по используемой СУБД).  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-класс](../../mfc/reference/cdaorecordset-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)   
 [Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
