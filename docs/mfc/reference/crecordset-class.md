---
title: "Класс CRecordset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
dev_langs: C++
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2375739fe4d8442d4ecb7a1514641d45de4a8be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crecordset-class"></a>CRecordset-класс
Представляет набор записей, выбранных из источника данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|Создает объект `CRecordset`. Производный класс необходимо предоставить конструктор, который вызывает следующее.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|Подготавливает для добавления новой записи. Вызовите `Update` для завершения добавления.|  
|[CRecordset::CanAppend](#canappend)|Возвращает ненулевое значение, если новые записи могут быть добавлены в набор записей через `AddNew` функции-члена.|  
|[CRecordset::CanBookmark](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|  
|[CRecordset::Cancel](#cancel)|Отменяет асинхронную операцию, или процесс из второго потока.|  
|[CRecordset::CancelUpdate](#cancelupdate)|Отменяет все имеющиеся обновления из-за `AddNew` или `Edit` операции.|  
|[CRecordset::CanRestart](#canrestart)|Возвращает ненулевое значение, если `Requery` может вызываться для выполнения запроса набора записей еще раз.|  
|[CRecordset::CanScroll](#canscroll)|Возвращает ненулевое значение, если можно прокручивать записи.|  
|[CRecordset::CanTransact](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|  
|[CRecordset::CanUpdate](#canupdate)|Возвращает ненулевое значение, если можно обновить набор записей (можно добавить, обновить или удалить записи).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|Вызывается для обработки ошибок, возникающих при выполнении записи выборки.|  
|[CRecordset::Close](#close)|Закрывает набора записей и ODBC **HSTMT** связанные с ним.|  
|[CRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. Явным образом, необходимо перейти к другой записи после удаления.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Вызывается для обмена пакетов строк данных из источника данных в набор записей. Реализует блочный обмен полей записей (Bulk RFX).|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Реализует запись обмен (полями записей RFX).|  
|[CRecordset::Edit](#edit)|Подготавливает для изменения текущей записи. Вызовите `Update` для завершения редактирования.|  
|[CRecordset::FlushResultSet](#flushresultset)|Возвращает ненулевое значение, если имеется другой результат, значение можно получить, когда с помощью предопределенного запроса.|  
|[CRecordset::GetBookmark](#getbookmark)|Присваивает значение закладки записи объект параметра.|  
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Вызывается для получения строки подключения по умолчанию.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Вызывается для получения строки SQL по умолчанию для выполнения.|  
|[CRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Возвращает число полей в наборе записей.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Возвращает определенные виды информации о поля в наборе записей.|  
|[CRecordset::GetRecordCount](#getrecordcount)|Возвращает число записей в наборе записей.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|Возвращает число записей, которые вы хотите получать в ходе одной выборки.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|Возвращает фактическое число строк, полученных во время выборки.|  
|[CRecordset::GetRowStatus](#getrowstatus)|Возвращает состояние строки после выборки.|  
|[CRecordset::GetSQL](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|  
|[CRecordset::GetStatus](#getstatus)|Возвращает состояние набора записей: индекс текущей записи и был ли получен окончательное количество записей.|  
|[CRecordset::GetTableName](#gettablename)|Возвращает имя таблицы, на которой основан набор записей.|  
|[CRecordset::IsBOF](#isbof)|Возвращает ненулевое значение, если набор записей был позиционирован перед первой записи. Отсутствует текущая запись.|  
|[CRecordset::IsDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей располагается на удаленную запись.|  
|[CRecordset::IsEOF](#iseof)|Возвращает ненулевое значение, если набор записей был помещен после последней записи. Отсутствует текущая запись.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи был изменен.|  
|[CRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение null (не имеет значения).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи можно задать значение null (значение не имеющая).|  
|[CRecordset::IsOpen](#isopen)|Возвращает ненулевое значение, если `Open` был вызван ранее.|  
|[CRecordset::Move](#move)|Устанавливает набор записей с заданным числом записей в текущей записи в любом направлении.|  
|[CRecordset::MoveFirst](#movefirst)|Помещает текущей записи на первой записи в наборе записей. Проверить `IsBOF` первой.|  
|[CRecordset::MoveLast](#movelast)|Помещает текущей записи на последней записи или последнего набора строк. Проверить `IsEOF` первой.|  
|[CRecordset::MoveNext](#movenext)|Помещает текущей записи к следующей записи или для следующего набора строк. Проверить `IsEOF` первой.|  
|[CRecordset::MovePrev](#moveprev)|Помещает текущей записи на предыдущей записи или в предыдущих строк. Проверить `IsBOF` первой.|  
|[CRecordset::OnSetOptions](#onsetoptions)|Вызывается, чтобы задать параметры (используется для выбора) для указанной инструкции ODBC.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Вызывается, чтобы задать параметры (используется при обновлении) для указанной инструкции ODBC.|  
|[CRecordset::Open](#open)|Открывает набор записей при извлечении таблицы или при выполнении запроса, который представляет набор записей.|  
|[CRecordset::RefreshRowset](#refreshrowset)|Обновляет данные и состояние указанные строки.|  
|[Метод CRecordset::Requery](#requery)|Выполнение запроса набора записей еще раз, чтобы обновить выбранные записи.|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Устанавливает набор записей на запись, соответствующую номер указанной записи.|  
|[CRecordset::SetBookmark](#setbookmark)|Устанавливает набор записей на записи, указанные на закладки.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|Помечает указанного поля текущей записи, как измененный.|  
|[CRecordset::SetFieldNull](#setfieldnull)|Задает значение указанного поля в текущей записи значение null (значение не имеющая).|  
|[CRecordset::SetLockingMode](#setlockingmode)|Задает режим блокировки «оптимистичный» блокировка (по умолчанию) или «пессимистической» блокировки. Определяет, как блокировки для обновления записей.|  
|[CRecordset::SetParamNull](#setparamnull)|Присваивает указанному параметру значение null (значение не имеющая).|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Помещает курсор на заданной строки в наборе строк.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|Указывает количество записей, которые вы хотите получить во время выборки.|  
|[CRecordset::Update](#update)|Завершает `AddNew` или `Edit` операции путем сохранения новых или измененных данных в источнике данных.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|Содержит дескриптор инструкции ODBC для набора записей. Введите `HSTMT`.|  
|[CRecordset::m_nFields](#m_nfields)|Содержит число элементов данных полей в наборе записей. Введите `UINT`.|  
|[CRecordset::m_nParams](#m_nparams)|Содержит количество элементов данных параметров в наборе записей. Введите `UINT`.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|Содержит указатель на `CDatabase` объекта, через который набор записей подключен к источнику данных.|  
|[CRecordset::m_strFilter](#m_strfilter)|Содержит `CString` , задающий язык SQL (Structured Query) `WHERE` предложения. Используется в качестве фильтра для выбора только те записи, которые соответствуют определенным критериям.|  
|[CRecordset::m_strSort](#m_strsort)|Содержит `CString` , указывающий SQL `ORDER BY` предложения. Используется для управления как записи сортируются.|  
  
## <a name="remarks"></a>Примечания  
 Известный как «наборы данных», `CRecordset` объектов обычно используются в двух формах: динамические подмножества данных и моментальные снимки. Динамический набор остается синхронизированной с обновления данных, внесенных другими пользователями. Моментальный снимок является статическим представлением данных. Каждая форма представляет набор записей, во время открытия набора записей фиксированным, но во время перехода к записи в подмножества, она отражает изменения, внесенные в запись впоследствии другими пользователями или других наборов записей в приложении.  
  
> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не классы Open Database Connectivity (ODBC), используйте класс [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) вместо него. Дополнительные сведения см. в статье [Обзор: программирования баз данных](../../data/data-access-programming-mfc-atl.md).  
  
 Для работы, независимо от типа набора записей, вы обычно набора записей для конкретного приложения создайте класс, производный от `CRecordset`. Наборы записей выберите записи из источника данных, а после этого можно:  
  
-   Прокручивать записи.  
  
-   Обновить записи и укажите режим блокировки.  
  
-   Фильтрация набора записей, чтобы ограничить записи, которые он выбирает из доступных в источнике данных.  
  
-   Выполните сортировку набора записей.  
  
-   Параметризация набора записей можно изменить выбранный для него, сведения, которые неизвестны до времени выполнения.  
  
 Чтобы использовать класс, открыть базу данных и создайте объект набора записей, передав конструктору указатель на `CDatabase` объект. Затем вызовите набора записей **откройте** функции-члене, где можно указать, является ли объект динамический или статический. Вызов **откройте** выбирает данные из источника данных. После открытия объекта набора записей, используйте элементы по функциям и данным члена прокручивать записи и обработать их. Доступные операции зависят от, является ли объект динамический или статический, будь то обновляемые или только для чтения (это зависит от возможностей источника данных, Open Database Connectivity (ODBC)), и того, реализуется ли пакетная выборка строк. Для обновления записей, которые могут были изменены или добавлены с момента **откройте** call, вызывающие этот объект **Requery** функции-члена. Вызвать объект **закрыть** члена функции и уничтожить объект после завершения работы с его.  
  
 В производном `CRecordset` класса, записывать обмен (полями записей RFX) и блочного обмена полями записей (Bulk RFX) используется для поддержки чтение и обновление полей в записи.  
  
 Дополнительные сведения о обмен полями записей и записи, см. в статьях [Обзор: программирования баз данных,](../../data/data-access-programming-mfc-atl.md), [записей (ODBC)](../../data/odbc/recordset-odbc.md), [набор записей: групповая выборка записей (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), и [поле обмен (полями записей RFX) записей](../../data/odbc/record-field-exchange-rfx.md). Фокус на подмножества и моментальные снимки, см. в статьях [динамический набор](../../data/odbc/dynaset.md) и [моментального снимка](../../data/odbc/snapshot.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="addnew"></a>CRecordset::AddNew  
 Подготавливает для добавления новой записи в таблицу.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [Requery](#requery) функции-члена для просмотра вновь добавленной записи. Поля записи изначально пусты. (В терминологии связанных баз данных, Null означает «предложений having значение отсутствует», а не является таким же, как **NULL** в C++.) Чтобы завершить операцию, необходимо вызвать [обновление](#update) функции-члена. **Обновление** сохраняет изменения в источнике данных.  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не удается вызвать `AddNew`. Это приведет к утверждение, вызвавшее сбой. Хотя класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `AddNew`Подготавливает новую, пустую запись, с помощью элементам данных полей. После вызова метода `AddNew`, задать нужные значения в элементам данных полей. (Нет необходимости вызывать [изменить](#edit) функции-члена для этой цели; используйте **изменить** только для существующих записей.) При последующем вызове **обновление**, измененные значения в поля элементов данных сохраняются в источнике данных.  
  
> [!CAUTION]
>  При переходе к новой записи перед вызовом метода **обновление**, новая запись теряется, а не предупреждение не выдается.  
  
 Если источник данных поддерживает транзакции, можно сделать ваш `AddNew` вызовов часть транзакции. Дополнительные сведения о транзакциях см. класс [CDatabase](../../mfc/reference/cdatabase-class.md). Обратите внимание, что необходимо вызвать [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) перед вызовом `AddNew`.  
  
> [!NOTE]
>  Для динамических подмножеств данных новые записи добавляются в набор записей как последнюю запись. Добавленных записей не добавляются к моментальным снимкам; необходимо вызвать **Requery** обновление набора записей.  
  
 Недопустимо для вызова `AddNew` для объекта recordset, **откройте** функция-член не был вызван. Объект `CDBException` возникает при вызове метода `AddNew` для набора записей, который не может быть добавлен к. Можно определить, является ли набор записей обновляемым путем вызова [CanAppend](#canappend).  
  
 Дополнительные сведения см. в следующих статьях: [набор записей: как наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), и [транзакции () ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Пример  
 См. в статье [транзакции: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="canappend"></a>CRecordset::CanAppend  
 Определяет, позволяет ли ранее открывавшихся набора записей для добавления новых записей.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей разрешает добавление новых записей; в противном случае — 0. `CanAppend`Возвращает 0, если открыть набор записей, только для чтения.  
  
##  <a name="canbookmark"></a>CRecordset::CanBookmark  
 Определяет, является ли набор записей позволяет помечать записей с помощью закладок.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей поддерживает закладки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не зависит от **CRecordset::useBookmarks** в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена. `CanBookmark`Указывает, является ли конкретного драйвера ODBC и курсор тип поддержки закладок. **CRecordset::useBookmarks** указывает, будет ли доступен, закладки, если они поддерживаются.  
  
> [!NOTE]
>  Закладки не поддерживаются на наборы последовательного доступа.  
  
 Дополнительные сведения о закладок и навигации по набору записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cancel"></a>CRecordset::Cancel  
 Запросы, что источник данных отменить асинхронную операцию в данный момент или процесса из второго потока.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что классы MFC ODBC больше не использовать асинхронную обработку; для выполнения асинхронной операции, необходимо напрямую вызвать функцию API-интерфейса ODBC **SQLSetConnectOption**. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в *Руководство программиста ODBC SDK*.  
  
##  <a name="cancelupdate"></a>CRecordset::CancelUpdate  
 Отменяет все ожидающие обновления, вызванные [изменить](#edit) или [AddNew](#addnew) операции, прежде чем [обновление](#update) вызывается.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция-член не применим к наборы записей, в которых используется выборка строк, так как не удается вызвать такие наборы записей **изменить**, `AddNew`, или **обновление**. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Если включена проверка автоматического поля «грязных», `CancelUpdate` переменных-членов приведет к восстановлению до значения, которые они имели до **изменить** или `AddNew` был вызван; в противном случае, останется изменения значений. По умолчанию, поле Автоматическая проверка включена при открытии набора записей. Чтобы отключить его, необходимо указать **CRecordset::noDirtyFieldCheck** в `dwOptions` параметр [откройте](#open) функции-члена.  
  
 Дополнительные сведения об обновлении данных см. в статье [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  
  
##  <a name="canrestart"></a>CRecordset::CanRestart  
 Определяет, позволяет ли набор записей перезапуска его запроса (чтобы обновить свои записи) путем вызова **Requery** функции-члена.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разрешено обновление; в противном случае — 0.  
  
##  <a name="canscroll"></a>CRecordset::CanScroll  
 Определяет, допускает ли прокрутка набора записей.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей допускает прокрутку; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о прокрутке см. в статье [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cantransact"></a>CRecordset::CanTransact  
 Определяет, позволяет ли набор записей транзакций.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей допускает транзакции. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>CRecordset::CanUpdate  
 Определяет, возможно ли обновление набора записей.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно обновить набор записей; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Набор записей может быть только для чтения, если базовый источник данных доступен только для чтения или если вы указали **CRecordset::readOnly** в `dwOptions` параметра при открытии набора записей.  
  
##  <a name="checkrowseterror"></a>CRecordset::CheckRowsetError  
 Вызывается для обработки ошибок, возникающих при выполнении записи выборки.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nRetCode`  
 Код возврата функции ODBC API. Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 Это виртуальная функция-член обрабатывает ошибки, возникающие при записи получены, и используется во время массовой выборке строк. Может потребоваться рассмотреть возможность переопределения `CheckRowsetError` для реализации обработки ошибок.  
  
 `CheckRowsetError`вызывается автоматически при выполнении операции курсора навигации, такие как **откройте**, **Requery**, или любой **переместить** операции. Он передается возвращаемое значение функции API-интерфейса ODBC **SQLExtendedFetch**. В следующей таблице перечислены возможные значения для `nRetCode` параметра.  
  
|nRetCode|Описание:|  
|--------------|-----------------|  
|**SQL_SUCCESS**|Функция успешно завершена; Дополнительные сведения не доступен.|  
|**SQL_SUCCESS_WITH_INFO**|Функция успешно завершена, возможно с Некритичная ошибка. Дополнительные сведения можно получить путем вызова **SQLError**.|  
|**SQL_NO_DATA_FOUND**|Будут выбраны все строки из результирующего набора.|  
|**ЗНАЧЕНИЕ SQL_ERROR**|Сбой функции. Дополнительные сведения можно получить путем вызова **SQLError**.|  
|**SQL_INVALID_HANDLE**|Сбой функции из-за дескриптора среды недопустимый дескриптора соединения и дескриптора инструкции. Это указывает на программную ошибку. Дополнительные сведения недоступны из **SQLError**.|  
|`SQL_STILL_EXECUTING`|Функция, которая была запущена асинхронно все еще выполняется. Обратите внимание, что по умолчанию MFC никогда не передает это значение для `CheckRowsetError`; MFC продолжит вызова **SQLExtendedFetch** до больше не возвращает `SQL_STILL_EXECUTING`.|  
  
 Дополнительные сведения о **SQLError**, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="close"></a>CRecordset::Close  
 Закрытие набора записей.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 ODBC **HSTMT** и всей памяти, освобождаются framework, выделенных для набора записей. Обычно после вызова **закрыть**, удалить C++ объекта набора записей, если он был выделен с помощью **новый**.  
  
 Можно вызвать **откройте** повторно после вызова **закрыть**. Это позволяет повторно использовать объекта набора записей. Можно вызвать **Requery**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>CRecordset::CRecordset  
 Создает объект `CRecordset`.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDatabase`  
 Содержит указатель на `CDatabase` объект или значение **NULL**. В противном случае **NULL** и `CDatabase` объекта **откройте** функция-член не был вызван соединиться с источником данных, набор записей пытается открыть его автоматически во время свой собственный **открыть**  вызова. Если передать **NULL**, `CDatabase` объект создается и подключение с использованием источника данных, указанный при производного класса набора записей с помощью классов.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать либо `CRecordset` напрямую или быть производным классом от приложения из `CRecordset`. Мастер классов можно использовать для формирования классов набора записей.  
  
> [!NOTE]
>  Производный класс *должен* предоставить свой собственный конструктор. В конструкторе производного класса, вызовите конструктор `CRecordset::CRecordset`, передавая ей соответствующие параметры вместе.  
  
 Передайте **NULL** конструктор набора записей иметь `CDatabase` объект создается и подключенным для вас автоматически. Это полезно сокращенное свойство, которое не требует создания и подключение `CDatabase` объекта до создания набора записей.  
  
### <a name="example"></a>Пример  
 Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
##  <a name="delete"></a>CRecordset::Delete  
 Удаляет текущую запись.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Примечания  
 После успешного удаления, элементам данных полей, присваивается значение Null, и необходимо явно вызвать один из **переместить** функции, чтобы отказаться от удаленной записи. После перемещения удаленные записи не удается вернуться к нему. Если источник данных поддерживает транзакции, то сможете **удалить** вызовов часть транзакции. Дополнительные сведения см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не удается вызвать **удалить**. Это приведет к утверждение, вызвавшее сбой. Хотя класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!CAUTION]
>  Набор записей должна быть обновлена, а должно быть допустимой записи в наборе записей текущего при вызове **удалить**; в противном случае возникает ошибка. Например, если удалить запись, но не прокручиваются новой записи перед вызовом метода **удаление** , **удалить** вызывает [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 В отличие от [AddNew](#addnew) и [изменить](#edit), вызов **удаление** должен следовать вызов [обновление](#update). Если **удалить** вызов завершается ошибкой, данные поля, элементы остаются без изменений.  
  
### <a name="example"></a>Пример  
 Этот пример набора записей, созданные на кадре функции. В примере предполагается существование `m_dbCust`, переменную-член типа `CDatabase` уже подключен к источнику данных.  
  
 [!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange  
 Вызывается для обмена пакетов строк данных из источника данных в набор записей. Реализует блочный обмен полей записей (Bulk RFX).  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](../../mfc/reference/cfieldexchange-class.md) объекта. Платформа уже будет установлен этот объект для указания контекста для операции обмена поля.  
  
### <a name="remarks"></a>Примечания  
 При реализации массовой выборки строк, платформа вызывает эту функцию-член автоматически передавать данные из источника данных объекта набора записей. `DoBulkFieldExchange`Привязывает параметризованные члены данных также в том случае, если таковая имеется, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей.  
  
 Если выборка строк не реализована, платформа вызывает [DoFieldExchange](#dofieldexchange). Для реализации массовой выборки строк, необходимо указать `CRecordset::useMultiRowFetch` параметр `dwOptions` параметр в [откройте](#open) функции-члена.  
  
> [!NOTE]
> `DoBulkFieldExchange`доступен только в том случае, если вы используете класс, производный от `CRecordset`. Если вы создали непосредственно из объекта набора записей `CRecordset`, необходимо вызвать [GetFieldValue](#getfieldvalue) функция-член для извлечения данных.  
  
 Блочный обмен полей записей (Bulk RFX) похож на обмен полями записей (RFX). Данные автоматически передается из источника данных объекта набора записей. Тем не менее, не может вызвать `AddNew`, **изменить**, **удаление**, или **обновление** для передачи изменений обратно в источник данных. Класс `CRecordset` в настоящее время не предоставляет механизма обновления пакетов строк данных; Однако можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**.  
  
 Обратите внимание, что ClassWizard не поддерживает блочный обмен полей записей; Таким образом, необходимо переопределить `DoBulkFieldExchange` вручную, вызовы функций Bulk RFX. Дополнительные сведения об этих функциях см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md).  
  
 Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения см. в статье [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="dofieldexchange"></a>CRecordset::DoFieldExchange  
 Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Реализует запись обмен (полями записей RFX).  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](../../mfc/reference/cfieldexchange-class.md) объекта. Платформа уже будет установлен этот объект для указания контекста для операции обмена поля.  
  
### <a name="remarks"></a>Примечания  
 Выборка строк не реализован, платформа вызывает эту функцию-член для обмена данными между элементами данных полей объекта набора записей и соответствующих столбцов текущей записи в источнике данных автоматически. `DoFieldExchange`Привязывает параметризованные члены данных также в том случае, если таковая имеется, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей.  
  
 Если реализована массовая выборка строк, платформа вызывает [DoBulkFieldExchange](#dobulkfieldexchange). Для реализации массовой выборки строк, необходимо указать `CRecordset::useMultiRowFetch` параметр `dwOptions` параметр в [откройте](#open) функции-члена.  
  
> [!NOTE]
> `DoFieldExchange`доступен только в том случае, если вы используете класс, производный от `CRecordset`. Если вы создали непосредственно из объекта набора записей `CRecordset`, необходимо вызвать [GetFieldValue](#getfieldvalue) функция-член для извлечения данных.  
  
 Обмен полей данных, называемый обмен полями записей (RFX) работает в обоих направлениях: члены данных полей объекта набора записей с полями записи в источнике данных и запись в источнике данных для объекта набора записей.  
  
 Единственным действием, обычно необходимо выполнить для реализации `DoFieldExchange` для набора записей производный класс является создание класса с ClassWizard и укажите имена и типы данных элементов данных полей. Можно также добавить код, что ClassWizard записывает для указания элементов данных параметров или обрабатывать любые столбцы, чтобы выполнить динамическую привязку. Дополнительные сведения см. в статье [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 При объявлении класса производного набора записей с ClassWizard мастер записывает переопределение `DoFieldExchange` , что аналогичный следующему примеру:  
  
 [!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 Дополнительные сведения о функциях RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md).  
  
 Дополнительные примеры и подробности о `DoFieldExchange`, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Общие сведения об RFX см. в статье [обмен полями записей](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="edit"></a>CRecordset::Edit  
 Позволяет вносить изменения в текущей записи.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **изменить**, элементами данных полей можно изменить путем сброса их значения напрямую. При последующем вызове завершения операции [обновление](#update) функции-члена для сохранения изменений в источнике данных.  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не удается вызвать **изменить**. Это приведет к утверждение, вызвавшее сбой. Хотя класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 **Изменить** сохраняет значения членов данных набора записей. При вызове метода **изменить**, внесите изменения, затем вызовите **изменить** , восстанавливаются значения записи он находился перед первым **изменить** вызова.  
  
 В некоторых случаях может потребоваться обновить столбец, делая Null (содержащий нет данных). Чтобы сделать это, вызовите [метод SetFieldNull](#setfieldnull) с параметром **TRUE** пометить поле Null; это также приводит обновляемого столбца. Если необходимо добавить поле записи с источником данных, несмотря на то, что его значение не изменилось, вызовите [SetFieldDirty](#setfielddirty) с параметром **TRUE**. Это работает, даже если оно имело значение Null.  
  
 Если источник данных поддерживает транзакции, то сможете **изменить** вызовов часть транзакции. Обратите внимание, что необходимо вызвать [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) перед вызовом **изменить** и после открытия набора записей. Также Обратите внимание, что вызов [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) не заменять вызов **обновление** для завершения **изменить** операции. Дополнительные сведения о транзакциях см. класс [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 В зависимости от текущего режима блокировки обновляемой записи может быть заблокировано **изменить** до вызова **обновление** или прокрутки к другой записи или может быть заблокирована только во время **изменить** вызова. Можно изменить режим блокировки с [SetLockingMode](#setlockingmode).  
  
 Предыдущее значение текущей записи восстанавливается при переходе к новой записи перед вызовом **обновление**. Объект `CDBException` возникает при вызове метода **изменить** для записей, который не может быть обновлен или если отсутствует текущая запись.  
  
 Дополнительные сведения см. в статьях [транзакции (ODBC)](../../data/odbc/transaction-odbc.md) и [набор записей: Блокировка записей (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>CRecordset::FlushResultSet  
 Возвращает следующий результирующий набор предопределенного запроса (хранимой процедуры), при наличии нескольких результирующих наборов.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если имеются дополнительные результирующие наборы, требуется получить; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать `FlushResultSet` только по окончании полностью с курсором текущего результирующего набора. Обратите внимание, что при извлечении к следующему результирующему набору, вызвав `FlushResultSet`, курсор не допускается для этого результирующего набора; следует вызывать [MoveNext](#movenext) после вызова функции-члена `FlushResultSet`.  
  
 Если предопределенного запроса использует выходной параметр или параметры ввода вывода, необходимо вызвать `FlushResultSet` пока не будет возвращено `FALSE` (значение 0), чтобы получить эти значения параметра.  
  
 `FlushResultSet`вызывает функцию ODBC API `SQLMoreResults`. Если `SQLMoreResults` возвращает `SQL_ERROR` или `SQL_INVALID_HANDLE`, затем `FlushResultSet` вызовет исключение. Дополнительные сведения о `SQLMoreResults`, см. в Windows SDK.  
  
 Хранимой процедуры должен связанный поля, если вы хотите вызвать `FlushResultSet`.  
  
### <a name="example"></a>Пример  
 В следующем коде предполагается, что `COutParamRecordset` — `CRecordset`-производного объекта на основании предопределенного запроса с входным и выходным параметром и наличие нескольких результирующих наборов. Обратите внимание, структура [DoFieldExchange](#dofieldexchange) переопределения.  
  
 [!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>CRecordset::GetBookmark  
 Получает значение закладки для текущей записи.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Параметры  
 `varBookmark`  
 Ссылку на [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, представляющий закладку на текущей записи.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить, поддерживаются ли закладки для объекта recordset, вызовите [CanBookmark](#canbookmark). Чтобы освободить закладки, если они поддерживаются, необходимо задать **CRecordset::useBookmarks** в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена.  
  
> [!NOTE]
>  Если закладок не поддерживается или недоступен, вызов `GetBookmark` приведет к созданию исключения. Закладки не поддерживаются на наборы последовательного доступа.  
  
 `GetBookmark`присваивает значение закладки для текущей записи `CDBVariant` объекта. Чтобы вернуться к этой записи в любое время после перемещения в другой записи, вызовите [SetBookmark](#setbookmark) с соответствующим свойством `CDBVariant` объекта.  
  
> [!NOTE]
>  После определенных операций по набору записей закладки больше не может быть допустимым. Например, при вызове метода `GetBookmark` следуют **Requery**, вы не сможете вернуться на запись с `SetBookmark`. Вызовите [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) для проверки, можно ли осуществить безопасный вызов `SetBookmark`.  
  
 Дополнительные сведения о закладок и навигации по набору записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="getdefaultconnect"></a>CRecordset::GetDefaultConnect  
 Вызывается для получения строки подключения по умолчанию.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий строку соединения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию-член для получения строки подключения по умолчанию для источника данных, на котором основан набор записей. ClassWizard реализует эту функцию для вас, указав тот же источник данных, используемого в ClassWizard для получения сведений о таблицах и столбцах. Вам будут, скорее всего, будет удобнее полагаться на это подключение по умолчанию при разработке приложения. Однако соединение по умолчанию может не подойти для пользователей приложения. Если это так, следует воссоздать этой функции, отменяя ClassWizard в версии. Дополнительные сведения о строках соединения см. в статье [источника данных (ODBC)](../../data/odbc/data-source-odbc.md).  
  
##  <a name="getdefaultsql"></a>CRecordset::GetDefaultSQL  
 Вызывается для получения строки SQL по умолчанию для выполнения.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий инструкцию SQL по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию-член для получения оператора SQL по умолчанию, на котором основан набор записей. Это может быть имя таблицы или SQL **ВЫБЕРИТЕ** инструкции.  
  
 Косвенно определите инструкцию SQL по умолчанию путем объявления класса набора записей с ClassWizard и ClassWizard не выполняет эту задачу автоматически.  
  
 Если требуется строка инструкции SQL для внутреннего использования, вызвать `GetSQL`, которая возвращает инструкцию SQL, используемую для выбора записей в наборе записей, когда он был открыт. Можно изменить строку SQL по умолчанию в ваш класс переопределение `GetDefaultSQL`. Например, можно указать стандартные запроса с помощью вызова **ВЫЗОВИТЕ** инструкции. (Обратите внимание, однако, если изменить `GetDefaultSQL`, необходимо также изменить `m_nFields` соответствует количеству столбцов в источнике данных.)  
  
 Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
> [!CAUTION]
>  Имя таблицы будет пустым, если платформа не удалось определить имя таблицы, если указано несколько имен таблиц или **ВЫЗОВИТЕ** инструкция не может быть интерпретирован. Обратите внимание, что при использовании **вызвать** инструкции, не должен вставить пробел между фигурными скобками и **вызвать** ключевое слово, и не должна вставлять пробел перед фигурную скобку или перед  **ВЫБЕРИТЕ** ключевое слово в **ВЫБЕРИТЕ** инструкции.  
  
##  <a name="getfieldvalue"></a>CRecordset::GetFieldValue  
 Получает поля данных в текущей записи.  
  
```  
void GetFieldValue(
    LPCTSTR lpszName,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CStringA& strValue);

 
void GetFieldValue(
    short nIndex,  
    CStringW& strValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Имя поля.  
  
 *varValu*e  
 Ссылку на [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, который будет хранить значение поля.  
  
 `nFieldType`  
 Тип данных ODBC C поля. Значение по умолчанию, **DEFAULT_FIELD_TYPE**, принудительно `GetFieldValue` определяет тип данных C из типа данных SQL на основе следующей таблице. В противном случае можно указать непосредственно типу данных, или выберите совместимый тип данных; Например, можно хранить любого типа данных в **SQL_C_CHAR**.  
  
|Тип данных C|Тип данных SQL|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 Дополнительные сведения о типах данных ODBC см. в разделах «Типы данных SQL» и «Типы данных C» в приложении Г. пакета SDK Windows.  
  
 `nIndex`  
 Отсчитываемый от нуля индекс поля.  
  
 `strValue`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, который будет хранить значение поля, преобразованные в текст, независимо от типа данных поля.  
  
### <a name="remarks"></a>Примечания  
 Поля можно искать по имени или по индексу. Значение поля можно хранить в любом `CDBVariant` объекта или `CString` объекта.  
  
 Если реализована массовая выборка строк, текущая запись всегда располагается на первой записи в наборе строк. Для использования `GetFieldValue` на запись в пределах определенного набора строк, необходимо сначала вызвать [SetRowsetCursorPosition](#setrowsetcursorposition) функции-члена для перемещения курсора на нужные строки в этом наборе строк. Затем вызовите `GetFieldValue` для этой строки. Для реализации массовой выборки строк, необходимо указать `CRecordset::useMultiRowFetch` параметр `dwOptions` параметр в [откройте](#open) функции-члена.  
  
 Можно использовать `GetFieldValue` для динамически выбирать поля во время выполнения, а не статически привязка их во время разработки. Например, если вы объявили непосредственно из объекта набора записей `CRecordset`, необходимо использовать `GetFieldValue` для извлечения полей данных, обмен полями записей (RFX) или блочный обмен полей записей (Bulk RFX), не реализованы.  
  
> [!NOTE]
>  При объявлении объекта набора записей не на основе `CRecordset`, не имеют загрузить библиотеку курсоров ODBC. Библиотека курсоров требует, чтобы набор записей по крайней мере один привязанного столбца; Тем не менее, при использовании `CRecordset` привязаны непосредственно, ни один из столбцов. Функции-члены [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) и [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) управления, будут ли загружать библиотеку курсоров.  
  
 `GetFieldValue`вызывает функцию ODBC API **SQLGetData**. Если драйвер выводит значение **SQL_NO_TOTAL** для фактическая длина значения поля `GetFieldValue` приводит к возникновению исключения. Дополнительные сведения о **SQLGetData**, см. в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано, как `GetFieldValue` объекта набора записей, объявленных непосредственно из `CRecordset`.  
  
 [!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  В отличие от классов DAO `CDaoRecordset`, `CRecordset` не имеет `SetFieldValue` функции-члена. Если вы создаете объект непосредственно из `CRecordset`, он фактически предназначены только для чтения.  
  
 Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount  
 Возвращает общее число полей объекта набора записей.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о создании наборов записей см. в статье [набор записей: Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getodbcfieldinfo"></a>CRecordset::GetODBCFieldInfo  
 Получает сведения о полях в наборе записей.  
  
```  
void GetODBCFieldInfo(
    LPCTSTR lpszName,  
    CODBCFieldInfo& fieldinfo);

 
void GetODBCFieldInfo(
    short nIndex,  
    CODBCFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Имя поля.  
  
 `fieldinfo`  
 Ссылку на `CODBCFieldInfo` структуры.  
  
 `nIndex`  
 Отсчитываемый от нуля индекс поля.  
  
### <a name="remarks"></a>Примечания  
 Одну версию функции позволяет искать поле по имени. Другая версия позволяет найти поле с индексом.  
  
 Описание сведений, возвращаемых в разделе [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) структуры.  
  
 Дополнительные сведения о создании наборов записей см. в статье [набор записей: Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getrecordcount"></a>CRecordset::GetRecordCount  
 Определяет размер набора записей.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей в наборе записей; 0, если набор записей не содержит записей; или -1, если число записей не может быть определено.  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Число записей как «пиковой, «наибольший номер записи, пока отображается, когда пользователь перемещает по записям. Общее количество записей известно только после пользователь был перемещен за пределы последнюю запись. Для повышения производительности, счетчик не обновляется при вызове `MoveLast`. Чтобы подсчитать записи самостоятельно, вызовите `MoveNext` пока `IsEOF` возвращает ненулевое значение. Добавление записи через **CRecordset:AddNew** и **обновление** увеличивает счетчик; удаление записи через `CRecordset::Delete` уменьшает значение счетчика.  
  
##  <a name="getrowsetsize"></a>CRecordset::GetRowsetSize  
 Получает текущее значение для числа строк, которые вы хотите получить во время операции выборки.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк для получения во время операции выборки.  
  
### <a name="remarks"></a>Примечания  
 Если вы используете выборка строк, размер набора строк по умолчанию при открытии набора записей — 25; в противном случае-1.  
  
 Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена. Чтобы изменить параметр размера набора строк, вызвать [SetRowsetSize](#setrowsetsize).  
  
 Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getrowsfetched"></a>CRecordset::GetRowsFetched  
 Определяет, сколько записей было фактически получено после выборки.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк, полученных из источника данных после операции выборки.  
  
### <a name="remarks"></a>Примечания  
 Это полезно в том случае, когда реализован выборка строк. Размер набора строк обычно указывает, сколько строк будет получен из выборки; Тем не менее общее число строк в наборе записей также влияет на количество строк, которые будут извлечены в наборе строк. Например, если набор записей содержит 10 записей по размер набора строк, равным 4, затем циклический перебор элементов в наборе записей путем вызова `MoveNext` приведет к окончательного набора строк, имеющие только 2 записи.  
  
 Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена. Чтобы определить размер набора строк, вызвать [SetRowsetSize](#setrowsetsize).  
  
 Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>CRecordset::GetRowStatus  
 Получение сведений о состоянии для строки в текущем наборе строк.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `wRow`  
 Единицы позицию строки в текущем наборе строк. Это значение находится в диапазоне от 1 до размера набора строк.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение состояния для строки. Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 `GetRowStatus`Возвращает значение, указывающее, любое изменение в состоянии, чтобы строка с момента его последнего, полученных из источника данных, или, нет соответствующей строки в `wRow` , которые были выбраны. В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение состояния|Описание:|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|Строка не содержит изменений.|  
|`SQL_ROW_UPDATED`|Строка была обновлена.|  
|`SQL_ROW_DELETED`|Строка была удалена.|  
|`SQL_ROW_ADDED`|Строка была добавлена.|  
|`SQL_ROW_ERROR`|Строки не удается извлечь из-за ошибки.|  
|`SQL_ROW_NOROW`|Нет строк, соответствующий `wRow`.|  
  
 Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLExtendedFetch** в Windows SDK.  
  
##  <a name="getstatus"></a>CRecordset::GetStatus  
 Определяет индекс текущей записи в наборе записей и ли наблюдалась последнюю запись.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rStatus`  
 Ссылку на **CRecordsetStatus** объекта. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 `CRecordset`пытается отслеживать индекс, но в некоторых случаях это может оказаться невозможным. В разделе [GetRecordCount](#getrecordcount) объяснение.  
  
 **CRecordsetStatus** структура имеет следующий вид:  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 Два элемента **CRecordsetStatus** имеют следующий смысл:  
  
- **m_lCurrentRecord** содержит отсчитываемый от нуля индекс текущей записи в наборе записей, если он известен. Если индекс не может определить, этот элемент содержит **AFX_CURRENT_RECORD_UNDEFINED** (-2). Если `IsBOF` — **TRUE** (пустой набор записей или попытка просмотра перед первой записи), затем **m_lCurrentRecord** равно **AFX_CURRENT_RECORD_BOF** (-1). Если на первой записи, затем он имеет значение 0, второй записи 1 и так далее.  
  
- **m_bRecordCountFinal** ненулевое значение, если было определено общее число записей в наборе записей. Обычно это необходимо сделать, начиная с первого набора записей и вызов `MoveNext` до `IsEOF` возвращает ненулевое значение. Если этого элемента равно нулю, запись подсчета, возвращенный `GetRecordCount`, если только «пиковой» число записей не -1.  
  
##  <a name="getsql"></a>CRecordset::GetSQL  
 Вызовите эту функцию-член для получения инструкции SQL, который был использован для выбора записей в наборе записей, когда он был открыт.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **const** ссылка на `CString` , содержащий инструкции SQL.  
  
### <a name="remarks"></a>Примечания  
 Как правило, это будет SQL **ВЫБЕРИТЕ** инструкции. Строка, возвращаемая функцией `GetSQL` доступно только для чтения.  
  
 Строка, возвращаемая функцией `GetSQL` обычно отличается от любую строку в набор записей в Вы передали `lpszSQL` параметр **откройте** функции-члена. Это обусловлено записей создает полная инструкция SQL, в зависимости от того, что Вы передали **откройте**, указанный с помощью классов, как указано в **m_strFilter** и `m_strSort` члены данных и любые параметры, которые могут указаны. Подробные сведения о как записей создает следующую инструкцию SQL, см. статью [набор записей: как наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода [откройте](#open).  
  
##  <a name="gettablename"></a>CRecordset::GetTableName  
 Возвращает имя таблицы SQL, на которой основан запрос набора записей.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **const** ссылка на `CString` , содержащую таблицу, имя, если набор записей из таблицы; в противном случае — пустая строка.  
  
### <a name="remarks"></a>Примечания  
 `GetTableName`Допустим, только если набор записей основан на таблице, не соединения нескольких таблиц или предопределенного запроса (хранимой процедуры). Имя доступно только для чтения.  
  
> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода [откройте](#open).  
  
##  <a name="isbof"></a>CRecordset::IsBOF  
 Возвращает ненулевое значение, если набор записей был позиционирован перед первой записи. Отсутствует текущая запись.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей не содержит записей или прокручен назад перед первой записью; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции-члена до перехода от записи к записи, чтобы узнать, является ли проверены перед первой записью в наборе записей. Можно также использовать `IsBOF` вместе с `IsEOF` чтобы определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода **откройте**, набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, который имеет по крайней мере одну запись, первая запись становится текущей записью и `IsBOF` возвращает 0.  
  
 Если первая запись становится текущей записи и вызывается `MovePrev`, `IsBOF` впоследствии возвращает ненулевое значение. Если `IsBOF` возвращает ненулевое значение, при вызове метода `MovePrev`, возникает ошибка. Если `IsBOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, которое требует текущей записи приведет к ошибке.  
  
### <a name="example"></a>Пример  
 В этом примере используется `IsBOF` и `IsEOF` для определения границ набора записей, как код выполняет прокрутку записей в обоих направлениях.  
  
 [!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>CRecordset::IsDeleted  
 Определяет, был ли удален текущей записи.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей располагается на удаленную запись; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если прокручивать записи и `IsDeleted` возвращает **TRUE** (не равно нулю), затем вы должны перейти к другой записи перед тем как выполнять никакие другие операции набора записей.  
  
 Результат `IsDeleted` зависит от многих факторов, таких как ваш тип recordset ли набор записей обновляемым, ли указанное **CRecordset::skipDeletedRecords** параметр при открытии набора записей, является ли ваш пакеты драйверов удаленных записей, и является ли несколько пользователей.  
  
 Дополнительные сведения о **CRecordset::skipDeletedRecords** и упаковки, драйвер [откройте](#open) функции-члена.  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не следует вызывать `IsDeleted`. Вместо этого необходимо вызвать [GetRowStatus](#getrowstatus) функции-члена. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="iseof"></a>CRecordset::IsEOF  
 Возвращает ненулевое значение, если набор записей был помещен после последней записи. Отсутствует текущая запись.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей не содержит записей или выполнен переход за последнюю запись; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, при переходе от записи к записи, чтобы узнать, является ли вышли за пределы последней записи в наборе записей. Можно также использовать `IsEOF` чтобы определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода **откройте**, набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, который имеет по крайней мере одну запись, первая запись становится текущей записью и `IsEOF` возвращает 0.  
  
 Если последняя запись становится текущей записью, при вызове `MoveNext`, `IsEOF` впоследствии возвращает ненулевое значение. Если `IsEOF` возвращает ненулевое значение, при вызове метода `MoveNext`, возникает ошибка. Если `IsEOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, которое требует текущей записи приведет к ошибке.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [IsBOF](#isbof).  
  
##  <a name="isfielddirty"></a>CRecordset::IsFieldDirty  
 Определяет, является ли элемент данных заданного поля изменились с момента последнего [изменить](#edit) или [AddNew](#addnew) был вызван.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения полей «грязных».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент данных заданного поля были изменены с момента вызова `AddNew` или **изменить**; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Данные в все измененными элементами данных полей должны быть переданы запись в источнике данных при обновлении текущей записи путем вызова [обновление](#update) функцию-член `CRecordset` (после вызова **изменить**или `AddNew`).  
  
> [!NOTE]
>  Эта функция-член не применим в наборы записей, в которых используется выборка строк. Если реализована массовая выборка строк, затем `IsFieldDirty` всегда будет возвращать **FALSE** и приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Вызов `IsFieldDirty` приведет к сбросу эффектов предыдущих вызовов [SetFieldDirty](#setfielddirty) так, как "грязные" состояние поля повторного вычисления. В `AddNew` случае, если текущее значение поля отличается от значения null псевдо поле перейдет в состояние «грязных». В **изменить** случае, если значение поля, отличается от кэшированное значение, то поле имеет состояние «грязных».  
  
 `IsFieldDirty`реализуется с помощью [DoFieldExchange](#dofieldexchange).  
  
 Дополнительные сведения о «грязный» флаг см. в статье [набор записей: как наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
##  <a name="isfieldnull"></a>CRecordset::IsFieldNull  
 Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение Null (не имеет значения).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения, если любое из полей имеют значение Null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент данных заданного поля будет отмечена как Null. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, чтобы определить, помечен ли элемент данных заданного поля в наборе записей как Null. (В терминологии связанных баз данных, Null означает «предложений having значение отсутствует», а не является таким же, как **NULL** в C++.) Если элемент данных поля помечен как Null, то он интерпретируется как столбца текущей записи, для которых нет значения.  
  
> [!NOTE]
>  Эта функция-член не применим в наборы записей, в которых используется выборка строк. Если реализована массовая выборка строк, затем `IsFieldNull` всегда будет возвращать **FALSE** и приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `IsFieldNull`реализуется с помощью [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isfieldnullable"></a>CRecordset::IsFieldNullable  
 Возвращает ненулевое значение, если указанное поле в текущей записи может иметь значение Null (значение не имеющая).  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения, если любое из полей может быть присвоено значение Null.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, чтобы определить, является ли элемент данных заданного поля «nullable» (может быть присвоено значение Null; C++ **NULL** не обязательно является Null, означающее, в терминологии связанных баз данных, «предложений having значение отсутствует»).  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не удается вызвать `IsFieldNullable`. Вместо этого необходимо вызвать [GetODBCFieldInfo](#getodbcfieldinfo) функции-члена для определения, является ли поле может быть присвоено значение Null. Обратите внимание, что всегда можно вызвать `GetODBCFieldInfo`, независимо от того, реализуется ли пакетная выборка строк. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Поле, которое не может иметь значение Null должны иметь значение. При попытке задать такому полю значение Null во время добавления или обновления записи источника данных отклоняет Добавление или обновление, и [обновление](#update) вызовет исключение. Исключение возникает при вызове **обновление**, не при вызове [метод SetFieldNull](#setfieldnull).  
  
 С помощью **NULL** первый аргумент функции будут относиться только к функции **outputColumn** поля не **param** поля. Например вызов  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 установит только **outputColumn** поля **NULL**; **param** полей не затрагиваются.  
  
 Для работы с **param** поля, необходимо указать фактический адрес отдельные **param** требуется для работы, такие как:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Это означает, что нельзя задать все **param** поля **NULL**, как и с **outputColumn** поля.  
  
 `IsFieldNullable`реализуется с помощью [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isopen"></a>CRecordset::IsOpen  
 Определяет, если набор записей открыт.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекта набора записей [откройте](#open) или [Requery](#requery) ранее вызвать функцию-член и набор записей не закрыт; в противном случае — 0.  
  
##  <a name="m_hstmt"></a>CRecordset::m_hstmt  
 Содержит дескриптор ODBC инструкции для структуры данных, типа **HSTMT**, связанные с набором записей.  
  
### <a name="remarks"></a>Примечания  
 Каждый запрос к источнику данных ODBC, связанный с **HSTMT**.  
  
> [!CAUTION]
>  Не используйте **m_hstmt** перед [откройте](#open) был вызван.  
  
 Обычно не требуется доступ к **HSTMT** напрямую, но которые могут потребоваться для прямого выполнения инструкций SQL. `ExecuteSQL` Функции-члена класса `CDatabase` приведен пример использования **m_hstmt**.  
  
##  <a name="m_nfields"></a>CRecordset::m_nFields  
 Содержит число элементов данных полей в классе набора записей. то есть, количество столбцов, выбранных в наборе записей из источника данных.  
  
### <a name="remarks"></a>Примечания  
 Необходимо инициализировать конструктор для класса записей `m_nFields` с правильным числом. Если групповая выборка строк не реализована, ClassWizard записывает инициализация автоматически при использовании для объявления класса набора записей. Можно также создать его вручную.  
  
 Платформа использует это число для управления взаимодействием между элементами данных полей и соответствующие столбцы текущей записи в источнике данных.  
  
> [!CAUTION]
>  Этот номер должен соответствовать числу «выходные столбцы», зарегистрированный в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) с параметром **CFieldExchange::outputColumn**.  
  
 Может привязать столбцы динамически, как описано в статье «набор записей: динамически столбцы привязки данных.» Если сделать это, необходимо увеличить число в `m_nFields` в соответствии с — число функции RFX и Bulk RFX вызова вашей `DoFieldExchange` или `DoBulkFieldExchange` функции-члена для динамически связанных столбцов.  
  
 Дополнительные сведения см. в статьях [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) и [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
 См. в статье [обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_nparams"></a>CRecordset::m_nParams  
 Содержит число элементов данных параметра в классе набора записей. число параметров, передаче с запросом набора записей.  
  
### <a name="remarks"></a>Примечания  
 Если класс набора записей элементов данных параметров, необходимо инициализировать конструктор для класса `m_nParams` с правильным числом. Значение `m_nParams` по умолчанию равно 0. При добавлении элементов данных параметров (которые необходимо сделать вручную) необходимо также вручную добавить инициализацию в конструкторе класса, в соответствии с числом параметров (который должен быть по крайней мере количество '' меток-заполнителей в вашей **m_strFilter**  или `m_strSort` строка).  
  
 Платформа использует этот номер, если он параметризует запрос набора записей.  
  
> [!CAUTION]
>  Этот номер должен соответствовать номеру «params», зарегистрированный в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) со значением параметра **CFieldExchange::inputParam**,  **CFieldExchange::param**, **CFieldExchange::outputParam**, или **CFieldExchange::inoutParam**.  
  
### <a name="example"></a>Пример  
  См. в статьях [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) и [обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_pdatabase"></a>CRecordset::m_pDatabase  
 Содержит указатель на `CDatabase` объекта, через который набор записей подключен к источнику данных.  
  
### <a name="remarks"></a>Примечания  
 Эта переменная задается двумя способами. Как правило, передать указатель на уже установлено `CDatabase` объекта при создании объекта набора записей. Если передать **NULL** вместо этого `CRecordset` создает `CDatabase` объекта для вас и подключает его. В любом случае `CRecordset` сохраняет указатель в этой переменной.  
  
 Обычно не требуется напрямую использовать указателем, сохраненным в **m_pDatabase**. При написании собственных расширений для `CRecordset`, однако может потребоваться использовать указатель. Например, может потребоваться указатель при вызове собственных `CDBException`s. Или он может понадобиться, если вам нужно сделать что-нибудь, используя те же `CDatabase` объекта, например выполняющихся транзакций, задание времени ожидания, или вызов `ExecuteSQL` функции-члена класса `CDatabase` для выполнения инструкций SQL непосредственно.  
  
##  <a name="m_strfilter"></a>CRecordset::m_strFilter  
 После создания объекта набора записей, но перед вызовом его **откройте** члена функции, используйте этот элемент данных для хранения `CString` содержащий SQL **ГДЕ** предложения.  
  
### <a name="remarks"></a>Примечания  
 Набор записей, эта строка используется для ограничения (или фильтр) записи, он выбирает во **откройте** или **Requery** вызова. Это полезно для выбора подмножества записей, например «всех менеджеров по продажам из Калифорнии» («состояние = Калифорния»). Синтаксис ODBC SQL **ГДЕ** предложение  
  
 `WHERE search-condition`  
  
 Обратите внимание, что не следует включать **ГДЕ** ключевое слово в строке. Структура предоставляет его.  
  
 Также можно параметризовать строки фильтра, поместив '' меток-заполнителей в его объявлении члена данных параметра в классе для каждого местозаполнителя и передача параметров в набор записей во время выполнения. Это позволяет создавать фильтр во время выполнения. Дополнительные сведения см. в статье [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Дополнительные сведения о SQL **ГДЕ** предложений, см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о выборе и фильтрации записей, см. в статье [набор записей: фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>CRecordset::m_strSort  
 После создания объекта набора записей, но перед вызовом его **откройте** члена функции, используйте этот элемент данных для хранения `CString` содержащий SQL **ORDER BY** предложения.  
  
### <a name="remarks"></a>Примечания  
 Эта строка используется в наборе записей отсортировать записи, он выбирает во **откройте** или **Requery** вызова. Эту функцию можно использовать для сортировки набора записей для одного или нескольких столбцов. Синтаксис ODBC SQL **ORDER BY** предложение  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 где спецификации сортировки — целое число или имя столбца. Можно также указать порядок по возрастанию или по убыванию (порядок по возрастанию по умолчанию) путем добавления «ASC» или «DESC» в списке столбцов в строке сортировки. Выбранные записи сортируются сначала по первому столбцу в списке, а затем второй и т. д. Например можно упорядочить набор записей «Заказчики» по фамилии, а затем по имени. Число столбцов, которые можно получить список зависит от источника данных. Дополнительные сведения см. в Windows SDK.  
  
 Обратите внимание, что не следует включать **ORDER BY** ключевое слово в строке. Структура предоставляет его.  
  
 Дополнительные сведения о предложениях SQL см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о сортировке записей, см. в статье [набор записей: сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>CRecordset::Move  
 Перемещает указатель текущей записи в наборе записей, либо вперед или назад.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>Параметры  
 `nRows`  
 Число строк для перемещения вперед или назад. Положительные значения Переход вперед, к концу набора записей. Отрицательные значения перемещение назад, к началу.  
  
 `wFetchType`  
 Определяет набор строк, **переместить** будет получена. Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 Если передается значение 0 для `nRows`, **переместить** обновление текущей записи; **Переместить** будет завершен любой текущей `AddNew` или **изменить** режиме и восстанавливается значение текущей записи перед `AddNew` или **изменить** был вызван.  
  
> [!NOTE]
>  При перемещении по набору записей, не могут пропускаться удаленных записей. В разделе [CRecordset::IsDeleted](#isdeleted) для получения дополнительной информации. При открытии `CRecordset` с **skipDeletedRecords** параметр, **переместить** утверждает Если `nRows` имеет значение 0. Это предотвращает обновление строк, удаляемых в других клиентских приложений, с помощью тех же данных. В разделе `dwOption` параметр в [откройте](#open) описание **skipDeletedRecords**.  
  
 **Переместить** перемещают набор записей по наборы строк. На основе значений для `nRows` и `wFetchType`, **переместить** извлекает соответствующий набор строк, а затем делает первую запись в этом наборе строк текущей записи. Если не реализована массовая выборка строк, размер набора строк всегда равно 1. При выборке набора строк, **переместить** напрямую вызывает [CheckRowsetError](#checkrowseterror) обрабатывать ошибки, возникающие в результате fetch функция-член.  
  
 В зависимости от значения, передать **переместить** эквивалентен других `CRecordset` функции-члены. В частности, значение `wFetchType` может указывать на функцию-член, интуитивно понятными и часто предпочтительный метод для перемещения к текущей записи.  
  
 В следующей таблице перечислены возможные значения для `wFetchType`, набор строк, **переместить** будет получена на основе `wFetchType` и `nRows`и любая функция эквивалентный член, соответствующий `wFetchType`.  
  
|wFetchType|Извлеченных строк|Эквивалентный член-функция|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE`(значение по умолчанию)|Начальный набор строк `nRows` строки из первой строки в текущем наборе строк.||  
|`SQL_FETCH_NEXT`|Следующий набор строк; `nRows` учитывается.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|Предыдущих строк; `nRows` учитывается.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|Первый набор строк в наборе записей; `nRows` учитывается.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|Последний полный набор строк в наборе записей; `nRows` учитывается.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|Если `nRows` > 0, набор строк, начинающийся `nRows` строк от начала набора записей. Если `nRows` < 0, набор строк, начинающийся `nRows` строк от конца набора записей. Если `nRows` = 0, то возвращается условие начало файла (BOF).|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|Набор строк, начиная со строки, значение которого закладки соответствует `nRows`.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  Для последовательного набора записей **переместить** допустимо только со значением `SQL_FETCH_NEXT` для `wFetchType`.  
  
> [!CAUTION]
>  Вызов **переместить** вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите [IsBOF](#isbof) и [IsEOF](#iseof).  
  
> [!NOTE]
>  Если выполнен переход за начало или конец набора записей ( `IsBOF` или `IsEOF` возвращает ненулевое значение), вызов **переместить** функция будет вызывать возможно `CDBException`. Например если `IsEOF` возвращает ненулевое значение, и `IsBOF` не так, нажмите `MoveNext` вызовет исключение, но `MovePrev` не будет.  
  
> [!NOTE]
>  При вызове метода **переместить** во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLExtendedFetch** в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>CRecordset::MoveFirst  
 Делает первую запись в первый набор строк текущей записи.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Примечания  
 Независимо от того выборка строк был реализован это всегда быть первой записи в наборе записей.  
  
 Нет необходимости вызывать **MoveFirst** сразу после открытия набора записей. В это время первой записи (если таковые имеются) автоматически является текущей записи.  
  
> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.  
  
> [!NOTE]
>  При перемещении по набору записей, не могут пропускаться удаленных записей. В разделе [IsDeleted](#isdeleted) функции-члена подробные сведения.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsBOF](#isbof).  
  
##  <a name="movelast"></a>CRecordset::MoveLast  
 Делает первую запись последней полный набор строк текущей записи.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Примечания  
 Если не реализована массовая выборка строк, набор записей имеет размер набора строк, равным 1, поэтому `MoveLast` просто перемещается к последнему записи в наборе записей.  
  
> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.  
  
> [!NOTE]
>  При перемещении по набору записей, не могут пропускаться удаленных записей. В разделе [IsDeleted](#isdeleted) функции-члена подробные сведения.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsBOF](#isbof).  
  
##  <a name="movenext"></a>CRecordset::MoveNext  
 Делает первую запись следующего набора строк текущей записи.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Примечания  
 Если не реализована массовая выборка строк, набор записей имеет размер набора строк, равным 1, поэтому `MoveNext` просто переходит к следующей записи.  
  
> [!NOTE]
>  При перемещении по набору записей, не могут пропускаться удаленных записей. В разделе [IsDeleted](#isdeleted) функции-члена подробные сведения.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.  
  
> [!NOTE]
>  Кроме того, рекомендуется вызывать `IsEOF` перед вызовом `MoveNext`. Например, если выполнен переход за пределами набора записей `IsEOF` возвращает ненулевое значение; в последующем вызове `MoveNext` вызывает исключение.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsBOF](#isbof).  
  
##  <a name="moveprev"></a>CRecordset::MovePrev  
 Делает первую запись в предыдущих строк текущей записи.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Примечания  
 Если не реализована массовая выборка строк, набор записей имеет размер набора строк, равным 1, поэтому `MovePrev` просто перемещается к предыдущей записи.  
  
> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.  
  
> [!NOTE]
>  При перемещении по набору записей, не могут пропускаться удаленных записей. В разделе [IsDeleted](#isdeleted) функции-члена подробные сведения.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.  
  
> [!NOTE]
>  Кроме того, рекомендуется вызывать `IsBOF` перед вызовом `MovePrev`. Например, если выполнена прокрутка до начала набора записей `IsBOF` возвращает ненулевое значение; в последующем вызове `MovePrev` вызывает исключение.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsBOF](#isbof).  
  
##  <a name="onsetoptions"></a>CRecordset::OnSetOptions  
 Вызывается, чтобы задать параметры (используется для выбора) для указанной инструкции ODBC.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Параметры  
 `hstmt`  
 **HSTMT** инструкции ODBC, параметры которого должны быть заданы.  
  
### <a name="remarks"></a>Примечания  
 Вызовите `OnSetOptions` для задания параметров (используется для выбора) для указанной инструкции ODBC. Платформа вызывает эту функцию-член для задания начальных параметров набора записей. `OnSetOptions`Определяет источник данных поддерживает прокручиваемые курсоры и параллелизм курсоров и соответствующим образом настраивает параметры набора записей. (В то время как `OnSetOptions` используется для операций выбора, `OnSetUpdateOptions` используется для операций обновления.)  
  
 Переопределить `OnSetOptions` для параметры set, относящиеся к драйверу или источнику данных. Например, если источник данных поддерживает открытие монопольного доступа, может переопределить `OnSetOptions` Чтобы воспользоваться преимуществами этой возможности.  
  
 Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions  
 Вызывается, чтобы задать параметры (используется при обновлении) для указанной инструкции ODBC.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Параметры  
 `hstmt`  
 **HSTMT** инструкции ODBC, параметры которого должны быть заданы.  
  
### <a name="remarks"></a>Примечания  
 Вызовите `OnSetUpdateOptions` для задания параметров (используется при обновлении) для указанной инструкции ODBC. Эта функция-член вызывается платформой, после создания HSTMT для обновления записей в наборе записей. (В то время как `OnSetOptions` используется для операций выбора, `OnSetUpdateOptions` используется для операций обновления.) `OnSetUpdateOptions` определяет источник данных поддерживает прокручиваемые курсоры и параллелизм курсоров и соответствующим образом настраивает параметры набора записей.  
  
 Переопределить `OnSetUpdateOptions` для задания параметров инструкции ODBC, прежде чем этот оператор используется для доступа к базе данных.  
  
 Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="open"></a>CRecordset::Open  
 Открывает набор записей при извлечении таблицы или при выполнении запроса, который представляет набор записей.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>Параметры  
 `nOpenType`  
 Примите значение по умолчанию **AFX_DB_USE_DEFAULT_TYPE**, или используйте одно из следующих значений **enum OpenType**:  
  
- **CRecordset::dynaset** набор записей с двунаправленным письмом прокрутки. Членство и порядок записей определяется при открытии набора записей, но изменения, сделанные другими пользователями на значения данных отображаются после операции выборки. Динамические подмножества данных называются также наборы записей, управляемых набором ключей.  
  
- **CRecordset::snapshot** статический набор записей с двунаправленным письмом прокрутки. Членство и порядок записей определяется при открытии набора записей; значения данных определяется в момент записи будут выбраны. Изменения, сделанные другими пользователями, не видны до закрывается и снова открыть набор записей.  
  
- **CRecordset::dynamic** набор записей с двунаправленным письмом прокрутки. Изменения, сделанные другими пользователями членства, упорядочение и данные значения видны следующей операции выборки. Обратите внимание, что многие драйверы ODBC не поддерживают этот тип набора записей.  
  
- **CRecordset::forwardOnly** набор записей доступным только для чтения с прокруткой только вперед.  
  
     Для `CRecordset`, значение по умолчанию — **CRecordset::snapshot**. Значение по умолчанию механизм позволяет мастеров Visual C++ для взаимодействия с и ODBC `CRecordset` и DAO `CDaoRecordset`, которые имеют различные значения по умолчанию.  
  
 Дополнительные сведения об этих типах записей см. в статье [записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения см. в статье «С помощью блока и Прокручиваемые курсоры» в Windows SDK.  
  
> [!CAUTION]
>  Если запрошенный тип не поддерживается, платформа создает исключение.  
  
 `lpszSQL`  
 Указатель на строку, содержащую одно из следующих:  
  
-   Объект **NULL** указателя.  
  
-   Имя таблицы.  
  
-   SQL **ВЫБЕРИТЕ** инструкции (при необходимости с помощью SQL **ГДЕ** или **ORDER BY** предложение).  
  
-   Объект **ВЫЗОВИТЕ** инструкцию, указав имя предопределенного запроса (хранимой процедуры). Будьте внимательны, не вставляйте пробел между фигурными скобками и **ВЫЗОВИТЕ** ключевое слово.  
  
 Дополнительные сведения о данной строки см. в таблице и обсуждение элемента ClassWizard роли под замечаниями.  
  
> [!NOTE]
>  Порядок столбцов в результирующий набор должен соответствовать порядку RFX или вызовы функций Bulk RFX вашей [DoFieldExchange](#dofieldexchange) или [DoBulkFieldExchange](#dobulkfieldexchange) функции переопределения.  
  
 `dwOptions`  
 Битовая маска, который можно задать сочетание значений, перечисленных ниже. Некоторые из них являются взаимоисключающими. Значение по умолчанию — **нет**.  
  
- **CRecordset::none** параметры не заданы. Значение этого параметра является взаимоисключающим с другими значениями. По умолчанию, можно обновить набор записей [изменить](#edit) или [удаление](#delete) и разрешает добавление новых записей с [AddNew](#addnew). Возможность обновления зависит от источника данных а также в `nOpenType` указать параметр. Оптимизация массового добавления недоступен. Выборка строк не реализована. Удаленные записи не пропускаются при перемещении по набору записей. Закладки недоступны. Проверка автоматического поля «грязных» реализуется.  
  
- **CRecordset::appendOnly** не допускают **изменить** или **удалить** на данном множестве записей. Разрешить `AddNew` только. Этот параметр является взаимоисключающим с **CRecordset::readOnly**.  
  
- **CRecordset::readOnly** открыть набор записей, только для чтения. Этот параметр является взаимоисключающим с **CRecordset::appendOnly**.  
  
- **CRecordset::optimizeBulkAdd** использовать подготовленной инструкции SQL для оптимизации Добавление много записей за один раз. Применяется только в том случае, если вы не используете функции API-интерфейса ODBC **SQLSetPos** обновление набора записей. Первое обновление определяет, какие поля отмечаются как грязные. Этот параметр является взаимоисключающим с `CRecordset::useMultiRowFetch`.  
  
- `CRecordset::useMultiRowFetch`Реализации массовой выборки строк, чтобы разрешить несколько строк для получения в операции одной выборки. Это является дополнительным, предназначенный для повышения производительности; Однако блочный обмен полей записей не поддерживается ClassWizard. Этот параметр является взаимоисключающим с **CRecordset::optimizeBulkAdd**. Обратите внимание, что при указании `CRecordset::useMultiRowFetch`, затем параметр **CRecordset::noDirtyFieldCheck** будет включен автоматически (двойной буферизации будет недоступен); в наборы записей последовательного доступа, параметр  **CRecordset::useExtendedFetch** будет включен автоматически. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
- **CRecordset::skipDeletedRecords** пропустить все удаленные записи при навигации по набору записей. Это приведет к снижению производительности в некоторых относительный выборки. Этот параметр не является действительным на наборы последовательного доступа. При вызове метода [переместить](#move) с `nRows` параметра равно 0 и **CRecordset::skipDeletedRecords** параметр, **переместить** будет assert. Обратите внимание, что **CRecordset::skipDeletedRecords** аналогичен *упаковки драйвер*, означающее, что удаленные строки удаляются из набора записей. Тем не менее если драйвер пакетов записей, затем он будет пропускать только те записи, которые можно удалить; он не будет пропускать записи, удаленные другим пользователям при открытом набора записей. **CRecordset::skipDeletedRecords** будет пропускать строки, удаленные другим пользователям.  
  
- **CRecordset::useBookmarks** можно использовать закладки для объекта recordset, если поддерживается. Закладки медленно извлечения данных, но также повысить производительность для перемещения данных. Не является допустимым на наборы последовательного доступа. Дополнительные сведения см. в статье [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
- **CRecordset::noDirtyFieldCheck** отключить автоматическое поля «грязных» проверки (двойной буферизации). Это улучшит производительность; Тем не менее, необходимо вручную пометить поля как «грязных» данных путем вызова `SetFieldDirty` и `SetFieldNull` функции-члены. Обратите внимание, что двойной буферизации в классе `CRecordset` аналогична двойной буферизации в классе `CDaoRecordset`. Однако в `CRecordset`, невозможно включить двойной буферизации для отдельных полей, можно включить ее для всех полей или отключить для всех полей. Обратите внимание, что при использовании параметра `CRecordset::useMultiRowFetch`, затем **CRecordset::noDirtyFieldCheck** будет включен автоматически, однако `SetFieldDirty` и `SetFieldNull` не может использоваться с наборами записей, выборка строк.  
  
- **CRecordset::executeDirect** не используйте подготовленной инструкции SQL. Для повышения производительности, укажите этот параметр, если **Requery** никогда не вызвать функцию-член.  
  
- **CRecordset::useExtendedFetch** реализуйте **SQLExtendedFetch** вместо **SQLFetch**. Эта возможность предназначена для реализации массовой выборки строк на наборы последовательного доступа. Если задан параметр `CRecordset::useMultiRowFetch` последовательным наборов записей, затем **CRecordset::useExtendedFetch** будет включен автоматически.  
  
- **CRecordset::userAllocMultiRowBuffers** пользователь выделит буферы хранения для данных. Используйте этот параметр в сочетании с `CRecordset::useMultiRowFetch` Если требуется выделить хранилища; в противном случае платформа будет автоматически выделить хранилище. Дополнительные сведения см. в статье [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Обратите внимание, что при указании **CRecordset::userAllocMultiRowBuffers** без указания `CRecordset::useMultiRowFetch` приведет к утверждение, вызвавшее сбой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CRecordset` объект был успешно открыт; в противном случае значение 0, если [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (если вызывается) возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать эту функцию-член для выполнения запроса определяется набор записей. Перед вызовом метода **откройте**, следует создать объекта набора записей.  
  
 Данному набору записей подключения к источнику данных зависит от того, как построить записей до вызова метода **откройте**. Если передать [CDatabase](../../mfc/reference/cdatabase-class.md) объекта набора записей конструктор, который не был подключен к источнику данных использует эту функцию-член [GetDefaultConnect](#getdefaultconnect) попытка открыть объект базы данных. При передаче **NULL** конструктору набора записей, конструктор создает `CDatabase` объекта, и **откройте** предпринимает попытку подключения объекта базы данных. Дополнительные сведения о закрытии набора записей и соединения в этих различных условиях см. в разделе [закрыть](#close).  
  
> [!NOTE]
>  Доступ к источнику данных через `CRecordset` всегда имеет доступ к объекту. В отличие от `CDaoRecordset` , нельзя использовать `CRecordset` объект, чтобы открыть источник данных с монопольным доступом.  
  
 При вызове **откройте**, запрос обычно SQL **ВЫБЕРИТЕ** инструкция, выбирает записи на основе критерия, показанные в следующей таблице.  
  
|Значение параметра lpszSQL|Определяется выбрано записей|Пример|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|Строка, возвращаемая функцией `GetDefaultSQL`.||  
|Имя таблицы SQL|Все столбцы из списка таблиц в `DoFieldExchange` или `DoBulkFieldExchange`.|`"Customer"`|  
|Имя предопределенного запроса (хранимой процедуры)|Столбцы, которые определен запрос для возврата.|`"{call OverDueAccts}"`|  
|**ВЫБЕРИТЕ** список столбцов **FROM** список таблиц|Указанные столбцы из указанной таблицы.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  Будьте осторожны, не вставляйте лишние пробелы в строке SQL. Например, если вставить пробел между фигурными скобками и **вызвать** ключевое слово, MFC будет неправильно интерпретировать строку SQL, как имя таблицы и вставить его в **ВЫБЕРИТЕ** инструкцию, которая приведет к исключения. Аналогичным образом, если предопределенные запросе используется выходной параметр, не вставлять пробел между фигурными скобками и '' символ. Наконец, не должен вставить пробел перед фигурная скобка в **вызвать** инструкции или до **ВЫБЕРИТЕ** ключевое слово в **ВЫБЕРИТЕ** инструкции.  
  
 Стандартные действия заключается в передаче **NULL** для **откройте**; в этом случае **откройте** вызовы [GetDefaultSQL](#getdefaultsql). Если вы используете производный `CRecordset` класса, **GetDefaultSQL** дает имена таблицы, указанной в ClassWizard. Вместо этого можно указать другие сведения в `lpszSQL` параметра.  
  
 Все передаваемые **откройте** создает окончательной строки SQL для запроса (в этой строке может содержаться SQL **ГДЕ** и **ORDER BY** добавляемый в конец предложения `lpszSQL` вы строка переданный), а затем выполняет запрос. Можно проверить сконструированный строку путем вызова [GetSQL](#getsql) после вызова **откройте**. Дополнительные сведения о том, как набор записей создает инструкцию SQL и выбирает записи, см. в статье [набор записей: как наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
 Элементами данных полей класса набора записей привязанные к столбцам выбранных данных. Если все записи, первая запись становится текущей записи.  
  
 Если вы хотите задать параметры для набора записей, таких как фильтр или сортировку, задавать их после создания объекта набора записей, но перед вызовом **откройте**. Если требуется для обновления записей в наборе записей после набор записей открыт, вызовите [Requery](#requery).  
  
 Дополнительные сведения, включая дополнительные примеры см. в статьях [записей (ODBC)](../../data/odbc/recordset-odbc.md), [набор записей: как наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), и [набор записей: Создание и закрытие Наборы записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
### <a name="example"></a>Пример  
 В следующих примерах кода показаны различные формы **откройте** вызова.  
  
 [!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>CRecordset::RefreshRowset  
 Обновляет данные и состояние для строки в текущем наборе строк.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Параметры  
 `wRow`  
 Единицы позицию строки в текущем наборе строк. Это значение может изменяться от нуля до размер набора строк.  
  
 `wLockType`  
 Значение, определяющее способ блокировки строки, после его обновления. Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 Если передается нулевое значение для `wRow`, то обновляются каждую строку в наборе строк.  
  
 Для использования `RefreshRowset`, необходимо реализована массовая выборка строк, указав **CRecordset::useMulitRowFetch** в диалоговом окне [откройте](#open) функции-члена.  
  
 `RefreshRowset`вызывает функцию ODBC API **SQLSetPos**. `wLockType` Указывает состояние блокировки строки после **SQLSetPos** был выполнен. В следующей таблице описаны возможные значения для `wLockType`.  
  
|wLockType|Описание:|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том же состоянии заблокирован или разблокирован, после появления `RefreshRowset` был вызван.|  
|`SQL_LOCK_EXCLUSIVE`|Драйвер или источник данных исключительно блокирует строку. Не все источники данных поддерживают этот тип блокировки.|  
|`SQL_LOCK_UNLOCK`|Драйвер или источник данных снимает блокировку строки. Не все источники данных поддерживают этот тип блокировки.|  
  
 Дополнительные сведения о **SQLSetPos**, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="requery"></a>Метод CRecordset::Requery  
 Перестраивает (обновления) набора записей.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей успешно перестроена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если все записи, первая запись становится текущей записи.  
  
 Чтобы набора записей для отражения, добавления и удаления, вы или другие пользователи, осуществляющие к источнику данных, необходимо перестроить набора записей путем вызова **Requery**. Если динамический набор записей, он автоматически отражает обновлений, которые вы или другие пользователи для его существующих записей (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать **Requery** для отражения изменений, с другими пользователями, а также добавления и удаления.  
  
 Для подмножества или моментального снимка, вызовите **Requery** любое время, в который необходимо перестроить набора записей с помощью нового фильтра или сортировки или новые значения параметров. Задайте свойства нового фильтра или сортировки задание новых значений для **m_strFilter** и `m_strSort` перед вызовом **Requery**. Установить новые параметры, назначив новые значения членов данных параметра перед вызовом **Requery**. Фильтрация и сортировка строк не меняются, можно повторно использовать в запросе, которая улучшает производительность.  
  
 Если произошел сбой попытки повторного построения recordset, закрывается набора записей. Перед вызовом метода **Requery**, можно определить, является ли набор записей можно опросить путем вызова `CanRestart` функции-члена. `CanRestart`не может гарантировать **Requery** будет выполнена успешно.  
  
> [!CAUTION]
>  Вызовите **Requery** только после вызова [откройте](#open).  
  
### <a name="example"></a>Пример  
 В этом примере перестраивается набор записей, чтобы применить другой порядок сортировки.  
  
 [!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>CRecordset::SetAbsolutePosition  
 Устанавливает набор записей на запись, соответствующую номер указанной записи.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>Параметры  
 `nRows`  
 Единицы порядковый номер для текущей записи в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 `SetAbsolutePosition`Перемещает указатель текущей записи, исходя из этого порядковый номер позиции.  
  
> [!NOTE]
>  Эта функция-член не является допустимым наборы последовательного доступа.  
  
 Для наборы записей ODBC абсолютное положение параметр 1, относится к первой записи в наборе записей; значение 0 указывает позицию начала файла (BOF).  
  
 Можно также передать отрицательные значения для `SetAbsolutePosition`. В этом случае позиции в наборе записей вычисляется из конца набора данных. Например `SetAbsolutePosition( -1 )` перемещает указатель текущей записи к последней записи в наборе записей.  
  
> [!NOTE]
>  Абсолютное положение не предназначен для использования в качестве символов-заместителей номер записи. Закладки-это по-прежнему рекомендуемый способ сохранения и возврат к заданной позиции, с момента изменения позиции записи при удалении предыдущего записей. Кроме того, вы не может быть уверенным, что данная запись будет иметь же абсолютное положение, если повторно набора записей создается снова, потому что порядок отдельных записей в наборе записей не обязательно, если он создается с помощью инструкции SQL, с помощью **ORDER BY** предложения.  
  
 Дополнительные сведения о перемещении по набору записей и закладки, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="setbookmark"></a>CRecordset::SetBookmark  
 Устанавливает набор записей на запись, содержащую указанную закладку.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Параметры  
 `varBookmark`  
 Ссылку на [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, содержащий значение для определенной записи.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить, поддерживаются ли закладки для объекта recordset, вызовите [CanBookmark](#canbookmark). Чтобы освободить закладки, если они поддерживаются, необходимо задать **CRecordset::useBookmarks** в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена.  
  
> [!NOTE]
>  Если закладок не поддерживается или недоступен, вызов `SetBookmark` приведет к созданию исключения. Закладки не поддерживаются на наборы последовательного доступа.  
  
 Для извлечения закладки для текущей записи, вызовите [GetBookmark](#getbookmark), сохраняющая значение закладки для `CDBVariant` объекта. Позже можно вернуться к этой записи, вызвав `SetBookmark` с помощью сохраненного закладок.  
  
> [!NOTE]
>  После определенных операций по набору записей, следует проверить сохраняемости закладки перед вызовом `SetBookmark`. Например, если получить закладки с `GetBookmark` и затем вызвать **Requery**, закладки является недействительным. Вызовите [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) для проверки, можно ли осуществить безопасный вызов `SetBookmark`.  
  
 Дополнительные сведения о закладок и навигации по набору записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="setfielddirty"></a>CRecordset::SetFieldDirty  
 Флаги элемента данных поля в наборе записей, как изменить или как неизмененные.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Содержит адрес элемента данных поля в наборе записей или **NULL**. Если **NULL**, помечаются все члены данных полей в наборе записей. (C++ **NULL** не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having значение отсутствует».)  
  
 `bDirty`  
 **Значение TRUE,** должен быть помечен как «грязным» (измененного) элемента данных поля. В противном случае **FALSE** должен быть помечен как «чистые» (без изменений) элемента данных поля.  
  
### <a name="remarks"></a>Примечания  
 Пометка поля как неизмененные гарантирует поле обновляется и создает меньше трафика SQL.  
  
> [!NOTE]
>  Эта функция-член не применим в наборы записей, в которых используется выборка строк. Если реализована массовая выборка строк, затем `SetFieldDirty` приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Метки framework изменить поля элементов данных, чтобы убедиться, что они будут записаны на запись в источнике данных с помощью механизма обмена (полями записей RFX) поле записи. Как правило, изменение значения поля устанавливает для поля «грязных» автоматически, поэтому редко нужно вызывать `SetFieldDirty` самостоятельно, но иногда может потребоваться убедитесь, что столбцы будут будут явно обновлены или вставлены независимо от того, какое значение поля данных член.  
  
> [!CAUTION]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).  
  
 С помощью **NULL** первый аргумент функции будут относиться только к функции **outputColumn** поля не **param** поля. Например вызов  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 установит только **outputColumn** поля **NULL**; **param** полей не затрагиваются.  
  
 Для работы с **param** поля, необходимо указать фактический адрес отдельные **param** требуется для работы, такие как:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Это означает, что нельзя задать все **param** поля **NULL**, как и с **outputColumn** поля.  
  
##  <a name="setfieldnull"></a>CRecordset::SetFieldNull  
 Флаги элемента данных поля в наборе записей, как Null (в частности, имеющая значение не) или как отличных от Null.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Содержит адрес элемента данных поля в наборе записей или **NULL**. Если **NULL**, помечаются все члены данных полей в наборе записей. (C++ **NULL** не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having значение отсутствует».)  
  
 `bNull`  
 Ненулевое значение, если элемента данных поля является помечен как имеющий значение (Null). В противном случае значение 0, если было отмечено как ненулевой элемента данных поля.  
  
### <a name="remarks"></a>Примечания  
 При добавлении новой записи в набор записей, все поля элементов данных изначально присваивается значение Null и помечен как «грязным» (измененного). При извлечении записи из источника данных, ее столбцы уже имеют значения либо равны Null.  
  
> [!NOTE]
>  Не вызывайте эту функцию-член с наборами записей, в которых используется выборка строк. Если реализована массовая выборка строк, при вызове `SetFieldNull` приводит к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 При желании специально для назначения поля текущей записи как не имеющий значения, вызывает `SetFieldNull` с `bNull` значение **TRUE** пометка его как Null. Если поле ранее было помечено как Null, и теперь требуется ему присваивается значение, просто установите его новым значением. Необходимо снять флаг Null с `SetFieldNull`. Чтобы определить, разрешено ли поле иметь значение Null, вызовите `IsFieldNullable`.  
  
> [!CAUTION]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).  
  
 С помощью **NULL** первый аргумент функции будут относиться только к функции **outputColumn** поля не **param** поля. Например вызов  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 установит только **outputColumn** поля **NULL**; **param** полей не затрагиваются.  
  
 Для работы с **param** поля, необходимо указать фактический адрес отдельные **param** требуется для работы, такие как:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Это означает, что нельзя задать все **param** поля **NULL**, как и с **outputColumn** поля.  
  
> [!NOTE]
>  При задании параметров значение Null, вызов `SetFieldNull` до открытых результатов в утверждение набора записей. В этом случае вызов [члена SetParamNull](#setparamnull).  
  
 `SetFieldNull`реализуется с помощью [DoFieldExchange](#dofieldexchange).  
  
##  <a name="setlockingmode"></a>CRecordset::SetLockingMode  
 Задает режим блокировки «оптимистичный» блокировка (по умолчанию) или «пессимистической» блокировки. Определяет, как блокировки для обновления записей.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>Параметры  
 `nMode`  
 Содержит одно из следующих значений из **перечисления LockMode**:  
  
- **Оптимистический** оптимистической блокировки блокировки записи, которая обновляется только при вызове **обновление**.  
  
- **Пессимистическая** пессимистической блокировки запись блокируется как можно скорее **изменить** вызывается и помещает их блокировки до **обновление** завершения вызова или переместить в новую запись.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член, если вам нужно указать, какие две стратегии блокировки записей набор записей используется для обновления. По умолчанию является режим блокировки набора записей **оптимистичный**. Вы можете изменять, особенно осторожны **пессимистическая** стратегия блокировки. Вызовите `SetLockingMode` после создания и открытия объекта набора записей, но перед вызовом **изменить**.  
  
##  <a name="setparamnull"></a>CRecordset::SetParamNull  
 Flags, параметр как Null (в частности, имеющая значение не) или как отличных от Null.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый с нуля индекс параметра.  
  
 `bNull`  
 Если **TRUE** (значение по умолчанию), параметр помечен как Null. В противном случае параметр помечен как отличных от Null.  
  
### <a name="remarks"></a>Примечания  
 В отличие от [метод SetFieldNull](#setfieldnull), можно вызвать `SetParamNull` до открытия набора записей.  
  
 `SetParamNull`обычно используется с предопределенные запросы (хранимые процедуры).  
  
##  <a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition  
 Перемещает курсор в строку в текущем наборе строк.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Параметры  
 `wRow`  
 Единицы позицию строки в текущем наборе строк. Это значение находится в диапазоне от 1 до размера набора строк.  
  
 `wLockType`  
 Значение, определяющее способ блокировки строки, после его обновления. Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 При реализации групповой выборки строк, извлекаемых записей наборы строк, где текущей записи первая запись в выбранных строк. Чтобы сделать текущую запись другой записью в наборе строк, вызов `SetRowsetCursorPosition`. Например, можно объединить `SetRowsetCursorPosition` с [GetFieldValue](#getfieldvalue) функции-члена для динамического извлечения данных из любой записи набора записей.  
  
 Для использования `SetRowsetCursorPosition`, необходимо реализована массовая выборка строк, указав `CRecordset::useMultiRowFetch` параметр `dwOptions` параметр в [откройте](#open) функции-члена.  
  
 `SetRowsetCursorPosition`вызывает функцию ODBC API **SQLSetPos**. `wLockType` Указывает состояние блокировки строки после **SQLSetPos** был выполнен. В следующей таблице описаны возможные значения для `wLockType`.  
  
|wLockType|Описание:|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том же состоянии заблокирован или разблокирован, после появления `SetRowsetCursorPosition` был вызван.|  
|`SQL_LOCK_EXCLUSIVE`|Драйвер или источник данных исключительно блокирует строку. Не все источники данных поддерживают этот тип блокировки.|  
|`SQL_LOCK_UNLOCK`|Драйвер или источник данных снимает блокировку строки. Не все источники данных поддерживают этот тип блокировки.|  
  
 Дополнительные сведения о **SQLSetPos**, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="setrowsetsize"></a>CRecordset::SetRowsetSize  
 Указывает количество записей, которые вы хотите получить во время выборки.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>Параметры  
 *dwNewRowsetSize*  
 Число строк для получения во время операции выборки.  
  
### <a name="remarks"></a>Примечания  
 Это виртуальная функция-член указывает, сколько строк необходимо получить во время одной выборки при использовании выборка строк. Для реализации массовой выборки строк, необходимо задать `CRecordset::useMultiRowFetch` в диалоговом окне `dwOptions` параметр [откройте](#open) функции-члена.  
  
> [!NOTE]
>  Вызов `SetRowsetSize` без реализации массовой выборки строк приведет к утверждение, вызвавшее сбой.  
  
 Вызовите `SetRowsetSize` перед вызовом **откройте** изначально задать размер набора строк для набора записей. Размер набора строк по умолчанию при реализации массовой выборки строк — 25.  
  
> [!NOTE]
>  Соблюдайте осторожность при вызове `SetRowsetSize`. Если вручную выделение хранилища для данных (как указано в **CRecordset::userAllocMultiRowBuffers** параметр dwOptions параметра в **откройте**), следует проверить, следует ли перераспределение буферы хранения после вызова метода `SetRowsetSize`, но перед выполнением любой операции перемещения курсора.  
  
 Чтобы получить текущее значение размера набора строк, вызвать [GetRowsetSize](#getrowsetsize).  
  
 Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="update"></a>CRecordset::Update  
 Завершает `AddNew` или **изменить** операции путем сохранения новых или измененных данных в источнике данных.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если одна запись успешно обновлен; в противном случае значение 0, если столбцы не были изменены. Если записи не были обновлены, или если более чем одна запись была обновлена, создается исключение. Исключение вызывается также для любого другого сбоя, в источнике данных.  
  
### <a name="remarks"></a>Примечания  
 Это функция-член вызывается после вызова [AddNew](#addnew) или [изменить](#edit) функции-члена. Этот вызов необходим для завершения `AddNew` или **изменить** операции.  
  
> [!NOTE]
>  Если реализована массовая выборка строк, не удается вызвать **обновление**. Это приведет к утверждение, вызвавшее сбой. Хотя класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Оба `AddNew` и **изменить** Подготовка буфера редактирования, в котором размещена добавленных или измененных данных для сохранения в источнике данных. **Обновление** сохраняет данные. Обновляются только поля, помеченные или обнаружены изменения.  
  
 Если источник данных поддерживает транзакции, то сможете **обновление** вызова (и соответствующим `AddNew` или **изменить** вызова) частью транзакции. Дополнительные сведения о транзакциях см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!CAUTION]
>  При вызове метода **обновление** без предварительного вызова `AddNew` или **изменить**, **обновление** вызывает `CDBException`. При вызове метода `AddNew` или **изменить**, необходимо вызвать **обновление** перед вызовом метода **переместить** операции или до закрытия соединения с источником данных или набора записей. В противном случае изменения будут утеряны и без уведомления.  
  
 Дополнительные сведения об обработке **обновление** сбоев, см. в статье [набор записей: как наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
### <a name="example"></a>Пример  
 См. в статье [транзакции: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDatabase-класс](../../mfc/reference/cdatabase-class.md)   
 [Класс CRecordView](../../mfc/reference/crecordview-class.md)
