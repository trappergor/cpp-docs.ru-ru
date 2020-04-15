---
title: CDaoRecordset класс
ms.date: 08/27/2018
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
ms.openlocfilehash: 5b4b2919405696c748ce01217ac82afeac316de2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377151"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset класс

Представляет набор записей, выбранных из источника данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Формирует объект `CDaoRecordset`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::AddNew](#addnew)|Готовится к добавлению новой записи. [Обновление](#update) вызова для завершения добавления.|
|[CDaoRecordset::CanAppend](#canappend)|Возвращает ненулевой, если новые записи могут быть добавлены к набору записей через функцию [члена AddNew.](#addnew)|
|[CDaoRecordset::CanBookmark](#canbookmark)|Возвращает ненулевой, если запись поддерживает закладки.|
|[CDaoRecordset::Отмена](#cancelupdate)|Отменяет все ожидающие обновления из-за операции [Edit](#edit) или [AddNew.](#addnew)|
|[CDaoRecordset::CanRestart](#canrestart)|Возвращает ненулевой, если [requery](#requery) может быть вызван для повторного выполнения запроса записи.|
|[CDaoRecordset::CanScroll](#canscroll)|Возвращает ненулевой, если вы можете прокрутить записи.|
|[CDaoRecordset::CanTransact](#cantransact)|Возвращает ненулевой, если источник данных поддерживает транзакции.|
|[CDaoRecordset::CanUpdate](#canupdate)|Возвращает ненулевой, если запись может быть обновлена (вы можете добавить, обновить или удалить записи).|
|[CDaoRecordset::Закрыть](#close)|Закрывает рекорд.|
|[CDaoRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. После удаления необходимо явно прокрутить другую запись.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между полевыми данными членов регистрации и соответствующей записью об источнике данных. Реализует обмен поля записи DAO (DFX).|
|[CDaoRecordset::Edit](#edit)|Подготовитесь к изменениям в текущей записи. Вызов `Update` для завершения досачения.|
|[CDaoRecordset:FillCache](#fillcache)|Заполняет все или часть локального кэша для объекта записи, который содержит данные из источника данных ODBC.|
|[CDaoRecordset:: Найти](#find)|Находит первое, следующее, предыдущее или последнее местоположение определенной строки в наборе рекордов типа динасена, который удовлетворяет указанным критериям и записывает текущую запись.|
|[CDaoRecordset::FindFirst](#findfirst)|Находит первую запись в динасет-типе или наборе моментальных снимков, который удовлетворяет указанным критериям и делает запись текущей записи.|
|[CDaoRecordset::FindLast](#findlast)|Находит последнюю запись в динасет-типе или наборе моментального типа, который удовлетворяет указанным критериям и делает запись текущей записи.|
|[CDaoRecordset:FindNext](#findnext)|Находит следующую запись в динасет-типе или наборе моментального типа, который удовлетворяет указанным критериям и делает запись текущей записи.|
|[CDaoRecordset:FindPrev](#findprev)|Находит предыдущую запись в динасет-типе или наборе моментальных снимков, который удовлетворяет указанным критериям и делает запись текущей записи.|
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Возвращает рекордное количество текущей записи объекта записи.|
|[CDaoRecordset::GetBookmark](#getbookmark)|Возвращает значение, представляющее закладку на записи.|
|[CDaoRecordset::GetCacheSize](#getcachesize)|Возвращает значение, окоторомывающее количество записей в наборе записей типа динасеза, содержащем данные, локально кэшированные из источника данных ODBC.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|Возвращает значение, которое определяет закладку первой записи в наборе записей, которые будут кэшированы.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|`CString` Возвращает имя индекса, который недавно использовался на индексированном типе `CDaoRecordset`таблицы.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Возвращает дату и время создания базовой таблицы, лежащей в `CDaoRecordset` основе объекта|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенного в конструкцию `CDaoRecordset` базовой таблицы, лежащей в основе объекта.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Возвращает имя источника данных по умолчанию.|
|[CDaoRecordset::GetDefaultS](#getdefaultsql)|Вызывается, чтобы получить строку по умолчанию S'L для выполнения.|
|[CDaoRecordset::GetEditMode](#geteditmode)|Возвращает значение, указывающее состояние редактирования для текущей записи.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее количество полей в наборе записей.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Возвращает конкретные виды информации о полях в наборе рекордов.|
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в рекорде.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|Извлекает количество индексов в таблице, лежащей в основе рекорда.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Возвращает различные виды информации об индексе.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Используется для определения последней добавленной или обновленной записи.|
|[CDaoRecordset:GetLockingMode](#getlockingmode)|Возвращает значение, указывающее тип блокировки, который действует во время редактирования.|
|[CDaoRecordset::GetName](#getname)|`CString` Возвращает имя рекорда.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|Извлекает текущее значение указанного параметра, хранящегося в базовом объекте DAOParameter.|
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Возвращает положение текущей записи в процентах от общего числа записей.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Возвращает количество записей, доступных в объекте записи.|
|[CDaoRecordset::GetS'L](#getsql)|Получает строку S'L, используемую для выбора записей для рекорда.|
|[CDaoRecordset::GetType](#gettype)|Вызывается для определения типа набора записей: тип таблицы, типа динасета или типа моментального снимка.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Возвращает `CString` значение, которое проверяет данные при входе в поле.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Извлекает текст, отображаемый, когда правило проверки не выполнено.|
|[CDaoRecordset::IsBOF](#isbof)|Возвращает ненулевой, если рекорд был расположен до первой записи. Отсутствует текущая запись.|
|[CDaoRecordset::Удаление](#isdeleted)|Возвращает ненулевой, если запись расположена на удаленной записи.|
|[CDaoRecordset::IsEOF](#iseof)|Возвращает ненулевой, если рекорд был расположен после последней записи. Отсутствует текущая запись.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Возвращает ненулевой, если указанное поле в текущей записи было изменено.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевой, если указанное поле в текущей записи Null (не имеет значения).|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Возвращает ненулевой, если указанное поле в текущем отчете может быть установлено на Null (не имеюще значения).|
|[CDaoRecordset::IsOpen](#isopen)|Возвращает ненулевой, если [Открытый](#open) был вызван ранее.|
|[CDaoRecordset::Движение](#move)|Позиции рекорда до определенного количества записей из текущего записи в любом направлении.|
|[CDaoRecordset::MoveFirst](#movefirst)|Позиции текущего рекорда на первом рекорде в рекорде.|
|[CDaoRecordset::MoveLast](#movelast)|Позиции текущего рекорда на последнем рекорде в рекорде.|
|[CDaoRecordset::MoveNext](#movenext)|Позиции текущего рекорда на следующий рекорд в recordset .|
|[CDaoRecordset::MovePrev](#moveprev)|Позиции текущего рекорда на предыдущем рекорде в рекорде.|
|[CDaoRecordset::Открыто](#open)|Создает новый набор записей из таблицы, динасета или снимка.|
|[CDaoRecordset::Requery](#requery)|Запускает запрос recordset снова для обновления выбранных записей.|
|[CDaoRecordset::Ищите](#seek)|Находит запись в индексируемом объекте рекорда типа таблицы, который удовлетворяет указанным критериям для текущего индекса и делает запись текущей записи.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Устанавливает рекордное количество текущего рекорда объекта записи.|
|[CDaoRecordset::SetBookmark](#setbookmark)|Позиция рекорда на записи, содержащей указанную закладку.|
|[CDaoRecordset::SetCacheSize](#setcachesize)|Устанавливает значение, окоторомывающее количество записей в наборе записей типа динасеза, содержащем данные, локально кэшированные из источника данных ODBC.|
|[CDaoRecordset::SetCacheStart](#setcachestart)|Устанавливает значение, которое определяет закладку первой записи в наборе записей, которые будут кэшированы.|
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Вызывается, чтобы установить индекс на таблице типа рекорда.|
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Отметки указанного поля в текущем отчете изменены.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Устанавливает значение указанного поля в текущем отчете на Null (не имеюще значения).|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Устанавливает значение поля в рекорде.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Устанавливает значение поля в рекорде null. (не имеет значения).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Устанавливает значение, указывающее тип блокировки для ввода в действие во время редактирования.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|Устанавливает текущее значение указанного параметра, хранящегося в базовом объекте DAOParameter|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Устанавливает текущее значение указанного параметра на Null (не имеющий значения).|
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Устанавливает положение текущей записи в место, соответствующее проценту от общего числа записей в записи.|
|[CDaoRecordset::Обновление](#update)|Завершает или `AddNew` `Edit` выполняет операцию, сохраняя новые или отредактированные данные в источнике данных.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Содержит флаг, указывающий, автоматически ли поля помечаются как измененные.|
|[CDaoRecordset::m_nFields](#m_nfields)|Содержит количество полевых данных в классе recordset и количество столбцов, выбранных рекордным набором из источника данных.|
|[CDaoRecordset::m_nParams](#m_nparams)|Содержит количество параметров данных в классе recordset - количество параметров, пройдено с запросом записи|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Указатель на интерфейс DAO, лежащий в основе объекта набора записей.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Исходная база данных для этого набора результатов. Содержит указатель на объект [CDaoDatabase.](../../mfc/reference/cdaodatabase-class.md)|
|[CDaoRecordset::m_strFilter](#m_strfilter)|Содержит строку, используемую для построения оператора S'L **WHERE.**|
|[CDaoRecordset::m_strSort](#m_strsort)|Содержит строку, используемую для построения оператора S'L **ORDER BY.**|

## <a name="remarks"></a>Remarks

Известные как "записи", `CDaoRecordset` объекты доступны в следующих трех формах:

- Записи типов таблиц представляют собой базовую таблицу, которую можно использовать для изучения, добавления, изменения или удаления записей из одной таблицы баз данных.

- Записи типа Dynaset являются результатом запроса, который может иметь обновляемые записи. Эти записи представляют собой набор записей, которые можно использовать для изучения, добавления, изменения или удаления записей из базовой таблицы или таблицы базы данных. Записи типа Dynaset могут содержать поля из одной или нескольких таблиц в базе данных.

- Записи типа моментального снимка — статическая копия набора записей, которые можно использовать для поиска данных или создания отчетов. Эти наборы записей могут содержать поля из одной или нескольких таблиц в базе данных, но не могут быть обновлены.

Каждая форма рекорда представляет собой набор записей, зафиксированных на момент открытия набора записей. При прокрутке записи в записи типа таблицы или в записи типа динасета он отражает изменения, внесенные в запись после открытия записи, либо другими пользователями, либо другими рекордами в вашем приложении. (Запись типа моментального снимка не может быть обновлена.) Вы можете `CDaoRecordset` использовать непосредственно или получить тип `CDaoRecordset`записи, специфичный для приложения, из . Можно выполнить следующее.

- Прокрутите записи.

- Установите индекс и быстро ищите записи с помощью [Seek](#seek) (только записи столового типа).

- Найдите записи на основе сравнения строк: "<", "к",\<"я", ">" или ">" (динасет-тип и моментальный тип записей).

- Обновите записи и укажите режим блокировки (кроме записей типа моментального снимка).

- Фильтр установить рекорд, чтобы ограничить, какие записи он выбирает из тех, которые доступны на источнике данных.

- Сортировать рекорд.

- Параметризировать рекорд, чтобы настроить его выбор с информацией, не известно до времени выполнения.

Класс `CDaoRecordset` поставляет интерфейс, похожий `CRecordset`на интерфейс класса. Основное отличие заключается в том, что класс `CDaoRecordset` получает доступ к данным через объект доступа к данным (DAO) на основе OLE. Класс `CRecordset` получает доступ к DBMS через Open Database Connectivity (ODBC) и драйвер ODBC для этого DBMS.

> [!NOTE]
> Классы баз данных DAO отличаются от классов баз данных MFC на основе open Database Connectivity (ODBC). Все названия классов баз данных DAO имеют префикс "CDao". Вы все еще можете получить доступ к источникам данных ODBC с классами DAO; Классы DAO обычно предлагают превосходные возможности, поскольку они специфичны для движка базы данных Microsoft Jet.

Вы можете `CDaoRecordset` использовать непосредственно или `CDaoRecordset`получить класс из . Чтобы использовать класс рекордов в любом случае, откройте базу данных и создайте `CDaoDatabase` объект, передав конструктору указатель на объект. Вы также можете `CDaoRecordset` построить объект и `CDaoDatabase` позволить MFC создать временный объект для вас. Затем позвоните в функцию [«Открытый](#open) член записи», указав, является ли объект рекордным типом таблицы, рекордным набором типа динасета или рекордным набором моментального набора. Вызов `Open` выбирает данные из базы данных и извлекает первую запись.

Используйте функции членов объекта и членов данных для прокрутки записей и работы над ними. Доступные операции зависят от того, является ли объект рекордным набором типов таблицы, рекордным набором типа динасета или рекордным набором моментального типа, и является ли он обновляемым или только для чтения — это зависит от возможности базы данных или источника данных Open Database Connectivity (ODBC). Чтобы обновить записи, которые могут `Open` быть изменены или добавлены после вызова, позвоните функции члена [Requery](#requery) объекта. Вызовите функцию `Close` члена объекта и уничтожьте объект, когда вы закончите с ним.

`CDaoRecordset`использует обмен поля записи DAO (DFX) для поддержки чтения и обновления полей записи через тип-безопасные члены вашего `CDaoRecordset` или-производного `CDaoRecordset`класса. Можно также реализовать динамическую привязку столбцов в базе данных без использования механизма DFX с помощью [GetFieldValue](#getfieldvalue) и [SetFieldValue.](#setfieldvalue)

Для получения соответствующей информации смотрите тему "Объект звукозаписи" в справке DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="cdaorecordsetaddnew"></a><a name="addnew"></a>CDaoRecordset::AddNew

Вызовите эту функцию участника, чтобы добавить новую запись в рекордный набор типа таблицы или динасета.

```
virtual void AddNew();
```

### <a name="remarks"></a>Remarks

Поля записи изначально являются null. (В терминологии базы данных Null означает «не имеющий ценности» и не является таким же, как NULL в СЗ.) Для завершения операции необходимо вызвать функцию участника [обновления.](#update) `Update`сохраняет изменения в источнике данных.

> [!CAUTION]
> Если вы отсечкиили запись, `Update`а затем прокрутите другую запись без вызова, ваши изменения теряются без предупреждения.

Если вы добавите запись к записи типа динасета, позвонив [addNew,](#addnew)запись будет видна в наборе записей и включена в базовую таблицу, где она становится видимой для любых новых `CDaoRecordset` объектов.

Положение нового рекорда зависит от типа рекорда:

- В динасете установленного типа, где вставляется новая запись, не гарантируется. Это поведение изменилось с Microsoft Jet 3.0 по причинам производительности и параллелизма. Если ваша цель состоит в том, чтобы сделать недавно добавленную запись текущей записи, получить закладку последней измененной записи и перейти к этой закладке:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- В таблице типа записи, для которой индекс был указан, записи возвращаются в нужном месте в порядке сортировки. Если индекс не указан, новые записи возвращаются в конце набора записей.

Запись, которая была актуальной до использования, `AddNew` остается актуальной. Если вы хотите сделать новый ток записи и запись поддерживает закладки, позвоните [SetBookmark](#setbookmark) к закладке, идентифицированной установкой свойства LastModified основного объекта записи DAO. Это полезно для определения значения для встречных (автоприразов) полей в добавленной записи. Для получения дополнительной информации, см [GetLastModifiedBookmark](#getlastmodifiedbookmark).

Если база данных поддерживает транзакции, вы можете сделать вызов `AddNew` частью транзакции. Для получения дополнительной информации [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)о транзакциях см. Обратите внимание, что вы должны позвонить [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) перед вызовом `AddNew`.

Незаконно вызывать `AddNew` запись, функция [открытого](#open) члена которого не была вызвана. A `CDaoException` брошен, если `AddNew` вы призываете к набору записей, которые не могут быть придательна. Вы можете определить, является ли набор обновлен, позвонив [в CanAppend.](#canappend)

Рамочные знаки изменили членов полевых данных, чтобы убедиться, что они будут записаны на запись об источнике данных механизмом обмена полями записей DAO (DFX). Изменение значения поля обычно автоматически устанавливает поле грязным, поэтому вам редко придется вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться гарантировать, что столбцы будут явно обновлены или вставлены независимо от того, какое значение находится в составе члена данных поля. Механизм DFX также использует **использование PSEUDO NULL.** Для получения дополнительной информации, см [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойного буферизации не используется, то изменение значения поля автоматически не устанавливает поле как грязное. В этом случае необходимо будет явно установить поле грязным. Флаг, содержащийся в [m_bCheckCacheForDirtyFields,](#m_bcheckcachefordirtyfields) контролирует эту автоматическую проверку поля.

> [!NOTE]
> Если записи являются двойными буферными (т.е. `CancelUpdate` включена автоматическая проверка поля), вызов `AddNew` `Edit` восстановит переменные членов к значениям, которые они имели до или были вызваны.

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "AddNew Method", "Метод отмены обновления", "Последнее изменение свойства" и "EditMode Property".

## <a name="cdaorecordsetcanappend"></a><a name="canappend"></a>CDaoRecordset::CanAppend

Вызовите эту функцию участника, чтобы определить, позволяет ли ранее открытый набор записей добавлять новые записи, вызывая функцию [члена AddNew.](#addnew)

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд позволяет добавлять новые записи; в противном случае 0. `CanAppend`вернется 0, если вы открыли рекорд, как только читать.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации, см.

## <a name="cdaorecordsetcanbookmark"></a><a name="canbookmark"></a>CDaoRecordset::CanBookmark

Позвоните в эту функцию участника, чтобы определить, позволяет ли ранее открытый рекордет по отдельности отмечать записи с помощью закладок.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд поддерживает закладки, в противном случае 0.

### <a name="remarks"></a>Remarks

Если вы используете записи, основанные исключительно на таблицах движков баз данных Microsoft Jet, закладки могут использоваться, за исключением записей типа моментального снимка, помеченных как записи только для переимки. Другие продукты базы данных (внешние источники данных ODBC) могут не поддерживать закладки.

Подробнее об этом читайте в теме "Недвижимость закладки" в справке DAO.

## <a name="cdaorecordsetcancelupdate"></a><a name="cancelupdate"></a>CDaoRecordset::Отмена

Функция `CancelUpdate` участника отменяет все ожидающие обновления из-за операции [Edit](#edit) или [AddNew.](#addnew)

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Remarks

Например, если приложение `Edit` вызывает `AddNew` функцию или функцию `CancelUpdate` участника и не `Edit` `AddNew` вызывает [обновление,](#update)отменяет любые изменения, внесенные после или вызванного.

> [!NOTE]
> Если записи являются двойными буферными (т.е. `CancelUpdate` включена автоматическая проверка поля), вызов `AddNew` `Edit` восстановит переменные членов к значениям, которые они имели до или были вызваны.

Если нет `Edit` или `AddNew` операция `CancelUpdate` не ожидается, вызывает MFC бросить исключение. Позвоните в функцию участника [GetEditMode,](#geteditmode) чтобы определить, есть ли отложенная операция, которая может быть отменена.

Для получения соответствующей информации смотрите тему "Метод отмены обновления" в справке DAO.

## <a name="cdaorecordsetcanrestart"></a><a name="canrestart"></a>CDaoRecordset::CanRestart

Вызовите эту функцию участника, чтобы определить, позволяет ли запись перезапустить `Requery` свой запрос (обновить свои записи) повызовув функцию участника.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `Requery` если можно вызвать для запуска запроса записи снова, в противном случае 0.

### <a name="remarks"></a>Remarks

Записи типов таблицы `Requery`не поддерживаются.

Если `Requery` она не поддерживается, позвоните [в Close,](#close) затем [откройте](#open) для обновления данных. Можно вызвать для `Requery` обновления базового параметра объекта записи после изменения значений параметра.

Для получения соответствующей информации смотрите тему "Перезапуск имущества" в справке DAO.

## <a name="cdaorecordsetcanscroll"></a><a name="canscroll"></a>CDaoRecordset::CanScroll

Вызовите эту функцию участника, чтобы определить, позволяет ли запись прокрутки.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вы можете прокрутить записи, в противном случае 0.

### <a name="remarks"></a>Remarks

Если вы называете [Открытый](#open) с, `dbForwardOnly`запись может только прокрутки вперед.

Для получения соответствующей информации смотрите тему "Позиционирование текущего указателя записи с DAO" в Справке DAO.

## <a name="cdaorecordsetcantransact"></a><a name="cantransact"></a>CDaoRecordset::CanTransact

Позвоните в эту функцию участника, чтобы определить, позволяет ли запись транзакции.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если основной источник данных поддерживает транзакции, в противном случае 0.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации смотрите тему "Недвижимость сделок" в справке DAO.

## <a name="cdaorecordsetcanupdate"></a><a name="canupdate"></a>CDaoRecordset::CanUpdate

Позвоните в эту функцию участника, чтобы определить, можно ли обновить набор записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись может быть обновлена (добавить, обновить и удалить записи), в противном случае 0.

### <a name="remarks"></a>Remarks

Запись может быть прочитана только в том случае, если основной `dbReadOnly` источник данных читается только или если вы указали для *nOptions,* когда вы позвонили [открыть](#open) для записи.

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "AddNew Method", "Метод удаления", "Метод удаления", "Метод обновления" и "Updatable Property".

## <a name="cdaorecordsetcdaorecordset"></a><a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset

Формирует объект `CDaoRecordset`.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) или значение NULL. Если не NULL `CDaoDatabase` и `Open` функция члена объекта не была вызвана для подключения его к источнику данных, запись пытается открыть его для вас во время своего собственного [открытого](#open) вызова. Если вы проходите `CDaoDatabase` NULL, объект строится и подключается для вас, используя информацию `CDaoRecordset`об источнике данных, указанную вы, если вы вывели свой класс recordset из .

### <a name="remarks"></a>Remarks

Вы можете `CDaoRecordset` использовать непосредственно или получить тип `CDaoRecordset`для конкретного приложения из . Вы можете использовать ClassWizard для получения классов записей.

> [!NOTE]
> Если вы `CDaoRecordset` получаете класс, ваш производный класс должен предоставить свой собственный конструктор. В конструкторе вашего производного `CDaoRecordset::CDaoRecordset`класса позвоните в конструктор, передав ему соответствующие параметры.

Передайте NULL своему конструктору `CDaoDatabase` записей, чтобы объект был построен и подключен для вас автоматически. Это полезный ярлык, который не требует, чтобы `CDaoDatabase` построить и подключить объект до построения вашего рекорда. Если `CDaoDatabase` объект не открыт, для вас также будет создан объект [CDaoWorkspace,](../../mfc/reference/cdaoworkspace-class.md) который использует рабочее пространство по умолчанию. Для получения дополнительной информации, см [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

## <a name="cdaorecordsetclose"></a><a name="close"></a>CDaoRecordset::Закрыть

Закрытие `CDaoRecordset` объекта удаляет его из коллекции открытых записей в связанной базе данных.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Поскольку `Close` `CDaoRecordset` объект не уничтожается, можно `Open` повторно использовать объект, вызывая один и тот же источник данных или другой источник данных.

Все незавершенные заявления [AddNew](#addnew) или [Edit](#edit) отменяются, а все ожидающие транзакции откатываются. Если вы хотите сохранить ожидающие дополнения или редиты, позвоните [в Update,](#update) прежде чем звонить `Close` для каждого набора записей.

Вы можете `Open` позвонить `Close`еще раз после вызова . Это позволяет повторно использовать объект записи. Лучшей альтернативой является вызов [Requery](#requery), если это возможно.

Для получения соответствующей информации смотрите тему "Закрыть метод" в справке DAO.

## <a name="cdaorecordsetdelete"></a><a name="delete"></a>CDaoRecordset::Delete

Вызовите эту функцию участника, чтобы удалить текущую запись в открытом объекте типа динасета или типе таблицы.

```
virtual void Delete();
```

### <a name="remarks"></a>Remarks

После успешного удаления, члены данных полевых данных записей настроены на значение Null, и вы должны явно вызвать одну из функций члена навигации recordset [(Move,](#move) [Seek,](#seek) [SetBookmark](#setbookmark)и так далее) для того, чтобы отойти от удаленной записи. При удалении записей из рекордного набора должна быть текущая `Delete`запись в записи, прежде чем вы позвоните; в противном случае, MFC бросает исключение.

`Delete`удаляет текущую запись и делает ее недоступной. Хотя вы не можете отсеивать или использовать удаленную запись, она остается актуальной. Однако после перехода к другой записи вы не сможете снова сделать удаленную запись.

> [!CAUTION]
> Запись должна быть updatable и не должно быть действительным током `Delete`записи в recordset, когда вы звоните . Например, если вы удалите запись, но не `Delete` прокрутите новую запись перед вызовом снова, `Delete` бросает [CDaoException](../../mfc/reference/cdaoexception-class.md).

Вы можете удалить запись, если вы используете транзакции, и вы называете [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) функции участника. Если базовая таблица является основной таблицей в отношении каскада удаления, удаление текущей записи может также удалить одну или несколько записей в иностранной таблице. Для получения дополнительной информации в справке DAO см.

В `AddNew` `Edit`отличие от `Delete` и , вызов не `Update`сопровождается вызовом .

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "AddNew Method", "Метод удаления", "Метод удаления", "Метод обновления" и "Updatable Property".

## <a name="cdaorecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CDaoRecordset::DoFieldExchange

Платформа призывает эту функцию члена автоматически обмениваться данными между полевыми данными объектов вашего объекта записи и соответствующими столбцов текущей записи источника данных.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Содержит указатель `CDaoFieldExchange` на объект. В рамках уже будет создан этот объект для определения контекста для операции по обмену полями.

### <a name="remarks"></a>Remarks

Он также связывает членов параметра данных, если таковые имеются, к заполнителям параметров в строке оператора S'L для выбора набора записей. Обмен полевыми данными, называемый DAO обмена полями записей (DFX), работает в обоих направлениях: от полевых данных объекта записи до полей записи на источнике данных и от записи об источнике данных до объекта записи. Если вы динамически привязываете столбцы, `DoFieldExchange`вам не требуется реализовывать.

Единственное действие, необходимое обычно `DoFieldExchange` для реализации для вашего производного класса записей, это создание класса с ClassWizard и указание имен и типов данных членов полевых данных. Вы также можете добавить код к тому, что пишет ClassWizard, чтобы указать параметры данных. Если все поля будут связаны динамически, эта функция будет неактивна, если не указать параметры данных.

Когда вы объявляете свой класс производных записей с `DoFieldExchange` ClassWizard, мастер записывает переопределение для вас, который напоминает следующий пример:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

## <a name="cdaorecordsetedit"></a><a name="edit"></a>CDaoRecordset::Edit

Вызовите эту функцию участника, чтобы позволить вносить изменения в текущую запись.

```
virtual void Edit();
```

### <a name="remarks"></a>Remarks

После вызова `Edit` функции участника изменения, внесенные в поля текущей записи, скопируются в буфер копирования. После внесения желаемых изменений `Update` в запись позвоните, чтобы сохранить изменения. `Edit`сохраняет значения членов данных записей. Если вы `Edit`звоните, вносят изменения, а затем звоните `Edit` снова, значения `Edit` записи восстанавливаются до того, что они были до первого звонка.

> [!CAUTION]
> Если вы отсечкиили запись, а затем `Update`выполнили любую операцию, которая перемещается на другую запись без первого вызова, ваши изменения теряются без предупреждения. Кроме того, при закрытии базы записей или родительской базы данных отредактированная запись отбрасывается без предупреждения.

В некоторых случаях можно обновить столбец, сделав его недействительным (не содержащим данных). Для этого позвоните `SetFieldNull` с параметром TRUE, чтобы отметить поле Null; это также приводит к обновлению столбца. Если вы хотите, чтобы поле было записано в источник данных, даже если его значение не изменилось, позвоните `SetFieldDirty` с параметром TRUE. Это работает, даже если поле имело значение Null.

Рамочные знаки изменили членов полевых данных, чтобы убедиться, что они будут записаны на запись об источнике данных механизмом обмена полями записей DAO (DFX). Изменение значения поля обычно автоматически устанавливает поле грязным, поэтому вам редко придется вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться гарантировать, что столбцы будут явно обновлены или вставлены независимо от того, какое значение находится в составе члена данных поля. Механизм DFX также использует **использование PSEUDO NULL.** Для получения дополнительной информации, см [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойного буферизации не используется, то изменение значения поля автоматически не устанавливает поле как грязное. В этом случае необходимо будет явно установить поле грязным. Флаг, содержащийся в [m_bCheckCacheForDirtyFields,](#m_bcheckcachefordirtyfields) контролирует эту автоматическую проверку поля.

Когда объект записи пессимистично заблокирован в многопользовательской среде, запись `Edit` остается заблокированной от времени, используемого до завершения обновления. Если запись оптимистически заблокирована, запись заблокирована и сравнивается с предварительно отредактированной записью непосредственно перед ее обновлением в базе данных. Если запись изменилась с `Edit`момента `Update` вызова, операция не удается, и MFC бросает исключение. Вы можете изменить режим `SetLockingMode`блокировки с .

> [!NOTE]
> Оптимистичная блокировка всегда используется на внешних форматах баз данных, таких как ODBC и устанавливаемый ISAM.

Текущая запись остается `Edit`актуальной после вызова. Для `Edit`вызова, должна быть текущая запись. Если нет текущей записи или если запись не относится к объекту типа открытого типа таблицы или динасета, происходит исключение. Вызов `Edit` вызывает `CDaoException` бросив при следующих условиях:

- Отсутствует текущая запись.

- База данных или набор записей только для чтения.

- Нет полей в записи updatable.

- База данных или набор записей была открыта для эксклюзивного использования другим пользователем.

- Другой пользователь заблокировал страницу, содержащую вашу запись.

Если источник данных поддерживает транзакции, можно сделать `Edit` вызов частью транзакции. Обратите внимание, `CDaoWorkspace::BeginTrans` что `Edit` вы должны позвонить до вызова и после открытия набора записей. Также обратите `CDaoWorkspace::CommitTrans` внимание, что вызов `Update` не `Edit` является заменой вызова для завершения операции. Для получения дополнительной информации `CDaoWorkspace`о транзакциях см.

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "AddNew Method", "Метод удаления", "Метод удаления", "Метод обновления" и "Updatable Property".

## <a name="cdaorecordsetfillcache"></a><a name="fillcache"></a>CDaoRecordset:FillCache

Вызовите эту функцию участника, чтобы кэшировать определенное количество записей из набора записей.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Параметры

*pSize*<br/>
Упогоняет количество строк для заполнения кэша. Если вы отпустите этот параметр, значение определяется параметром свойства CacheSize базового объекта DAO.

*pBookmark*<br/>
[COleVariant,](../../mfc/reference/colevariant-class.md) указывающий на закладку. Кэш заполняется, начиная с записи, указанной этой закладкой. Если вы отпустите этот параметр, кэш заполняется, начиная с записи, указанной свойством CacheStart базового объекта DAO.

### <a name="remarks"></a>Remarks

Кэширование повышает производительность приложения, которое получает или получает данные с удаленного сервера. Кэш — это пространство в локальной памяти, в мещаве данные, полученные с последнего времени с сервера, исходя из предположения, что данные, вероятно, будут запрошены снова во время работы приложения. При запросе данных движок базы данных Microsoft Jet сначала проверяет кэш данных, а не изыскиего их с сервера, что занимает больше времени. Использование кэширования данных в источниках данных, не относящих ODBC, не влияет, так как данные не сохраняются в кэше.

Вместо того, чтобы ждать заполнения кэша записями по мере их извлечения, можно в `FillCache` любое время явно заполнить кэш, позвонив в функцию участника. Это более быстрый способ заполнить `FillCache` кэш, потому что получает несколько записей одновременно, а не по одному за раз. Например, во время отображения каждого экрана записей `FillCache` можно получить вызов приложения, чтобы получить следующий скриншот записей.

Любая база данных ODBC, доступ к ней будут иметь объекты записей, может иметь локальный кэш. Чтобы создать кэш, откройте объект записи из удаленного `SetCacheSize` источника `SetCacheStart` данных, а затем вызовите функции и функции участника набора записей. Если *lSize* и *lBookmark* создают диапазон, который частично `SetCacheSize` или `SetCacheStart`полностью находится за пределами диапазона, указанного и, часть рекорда за пределами этого диапазона игнорируется и не загружается в кэш. Если `FillCache` запрашивает больше записей, чем остается в удаленном источнике данных, извлекаются только оставшиеся записи, и никаких исключений не брасывает.

Записи, извлеченные из кэша, не отражают изменений, внесенных одновременно с исходными данными другими пользователями.

`FillCache`получает только записи, которые еще не кэшированы. Чтобы заставить обновить все кэшированные `SetCacheSize` данные, позвоните функции участника `SetCacheSize` с параметром *lSize,* равным 0, позвоните снова с `FillCache`параметром *lSize,* равным размеру кэша, который вы первоначально запрашивали, а затем позвоните.

Для получения соответствующей информации смотрите тему "Метод заполнения cache" в справке DAO.

## <a name="cdaorecordsetfind"></a><a name="find"></a>CDaoRecordset:: Найти

Вызовите эту функцию участника, чтобы найти определенную строку в динасене- или моментальном типе рекордсета с помощью оператора сравнения.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lFindType*<br/>
Значение, указывающее тип желаемой операции «Найти». Вы можете выбрать

- AFX_DAO_NEXT Найти следующее место строки.

- AFX_DAO_PREV Найти предыдущее местоположение соответствующей строки.

- AFX_DAO_FIRST Найти первое место соответствующей строки.

- AFX_DAO_LAST Найти последнее местоположение соответствующей строки.

*lpszFilter*<br/>
Строка выражения (например, **положение О ГДЕ** в заявлении S'L без слова **ГДЕ**) используется для поиска записи. Пример:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Вы можете найти первый, следующий, предыдущий или последний экземпляр строки. `Find`является виртуальной функцией, так что вы можете переопределить его и добавить свою собственную реализацию. `FindFirst`Функции `FindLast` `FindNext`, `FindPrev` и функции `Find` участника вызывают функцию `Find` участника, так что вы можете использовать для управления поведением всех операций Поиска.

Чтобы найти запись в наборе записей типа таблицы, позвоните в функцию участника [Seek.](#seek)

> [!TIP]
> Чем меньше набор записей у вас `Find` есть, тем более эффективным будет. В целом, и особенно с данными ODBC, лучше создать новый запрос, который получает только записи, которые вы хотите.

Для получения соответствующей информации смотрите тему "Найтипервый, FindLast, FindNext, Найти Предыдущие методы" в Справке DAO.

## <a name="cdaorecordsetfindfirst"></a><a name="findfirst"></a>CDaoRecordset::FindFirst

Вызовите эту функцию участника, чтобы найти первую запись, которая соответствует указанному условию.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строка выражения (например, **положение О ГДЕ** в заявлении S'L без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Функция `FindFirst` участника начинает свой поиск с начала набора записей и выполняет поиск до конца набора записей.

Если вы хотите включить все записи в поиск (а не только те, которые отвечают определенному состоянию) используйте одну из операций Move для перехода от записи к записи. Чтобы найти запись в наборе записей `Seek` типа таблицы, позвоните функции участника.

Если запись, соответствующая критериям, не находится, текущий указатель записи не определен и `FindFirst` возвращается ноль. Если запись содержит более одной записи, которая удовлетворяет критериям, `FindFirst` находит `FindNext` первое явление, находит следующее явление и так далее.

> [!CAUTION]
> Если вы отсечките текущую запись, `Update` не забудьте сохранить изменения, позвонив в функцию участника, прежде чем перейти к другой записи. Если вы переходите на другую запись без обновления, ваши изменения теряются без предупреждения.

Участник `Find` выполняет поиск по месту нахождения и в направлении, указанном в следующей таблице:

|Поиск операций|Begin|Направление поиска|
|---------------------|-----------|----------------------|
|`FindFirst`|Начало рекорда|Конец рекорда|
|`FindLast`|Конец рекорда|Начало рекорда|
|`FindNext`|Текущий рекорд|Конец рекорда|
|`FindPrevious`|Текущий рекорд|Начало рекорда|

> [!NOTE]
> При вызове `FindLast`движок базы данных Microsoft Jet полностью заполняет ваш рекорд до начала поиска, если это еще не сделано. Первый поиск может занять больше времени, чем последующие поиски.

Использование одной из операций Поиска не `MoveFirst` `MoveNext`то же самое, как вызов или , однако, который просто делает первый или следующий ток записи без указания условия. Вы можете следить за операцией «Поиск» с помощью операции «Движение».

Имейте в виду следующее при использовании операций «Найти»:

- Если `Find` возврат ненулевой, текущая запись не определена. В этом случае необходимо переместить текущий указатель записи к действительной записи.

- Нельзя использовать операцию «Найти» с помощью набора записей типа моментального снимка только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты сша (месяц-день), даже если вы не используете американскую версию движка базы данных Microsoft Jet; в противном случае соответствующие записи могут не быть найдены.

- При работе с базами данных ODBC и большими динамитами вы можете обнаружить, что использование операций «Найти» происходит медленно, особенно при работе с большими рекордами. Вы можете повысить производительность, используя запросы с помощью индивидуальных **предложений ORDERBY** или **WHERE,** запросов параметров или `CDaoQuerydef` объектов, которые извлекают определенные индексированные записи.

Для получения соответствующей информации смотрите тему "Найтипервый, FindLast, FindNext, Найти Предыдущие методы" в Справке DAO.

## <a name="cdaorecordsetfindlast"></a><a name="findlast"></a>CDaoRecordset::FindLast

Вызовите эту функцию участника, чтобы найти последнюю запись, которая соответствует указанному условию.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строка выражения (например, **положение О ГДЕ** в заявлении S'L без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Функция `FindLast` участника начинает поиск в конце набора записей и выполняет поиск в обратном направлении к началу набора записей.

Если вы хотите включить все записи в поиск (а не только те, которые отвечают определенному состоянию) используйте одну из операций Move для перехода от записи к записи. Чтобы найти запись в наборе записей `Seek` типа таблицы, позвоните функции участника.

Если запись, соответствующая критериям, не находится, текущий указатель записи не определен и `FindLast` возвращается ноль. Если запись содержит более одной записи, которая удовлетворяет критериям, `FindFirst` находит `FindNext` первое явление, находит следующее явление после первого появления и так далее.

> [!CAUTION]
> Если вы отсечките текущую запись, `Update` убедитесь, что вы сохраните изменения, позвонив в функцию участника, прежде чем перейти к другой записи. Если вы переходите на другую запись без обновления, ваши изменения теряются без предупреждения.

Использование одной из операций Поиска не `MoveFirst` `MoveNext`то же самое, как вызов или , однако, который просто делает первый или следующий ток записи без указания условия. Вы можете следить за операцией «Поиск» с помощью операции «Движение».

Имейте в виду следующее при использовании операций «Найти»:

- Если `Find` возврат ненулевой, текущая запись не определена. В этом случае необходимо переместить текущий указатель записи к действительной записи.

- Нельзя использовать операцию «Найти» с помощью набора записей типа моментального снимка только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты сша (месяц-день), даже если вы не используете американскую версию движка базы данных Microsoft Jet; в противном случае соответствующие записи могут не быть найдены.

- При работе с базами данных ODBC и большими динамитами вы можете обнаружить, что использование операций «Найти» происходит медленно, особенно при работе с большими рекордами. Вы можете повысить производительность, используя запросы с помощью индивидуальных **предложений ORDERBY** или **WHERE,** запросов параметров или `CDaoQuerydef` объектов, которые извлекают определенные индексированные записи.

Для получения соответствующей информации смотрите тему "Найтипервый, FindLast, FindNext, Найти Предыдущие методы" в Справке DAO.

## <a name="cdaorecordsetfindnext"></a><a name="findnext"></a>CDaoRecordset:FindNext

Вызовите эту функцию участника, чтобы найти следующую запись, которая соответствует указанному условию.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строка выражения (например, **положение О ГДЕ** в заявлении S'L без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Функция `FindNext` участника начинает поиск в текущей записи и выполняет поиск до конца набора записей.

Если вы хотите включить все записи в поиск (а не только те, которые отвечают определенному состоянию) используйте одну из операций Move для перехода от записи к записи. Чтобы найти запись в наборе записей `Seek` типа таблицы, позвоните функции участника.

Если запись, соответствующая критериям, не находится, текущий указатель записи не определен и `FindNext` возвращается ноль. Если запись содержит более одной записи, которая удовлетворяет критериям, `FindFirst` находит `FindNext` первое явление, находит следующее явление и так далее.

> [!CAUTION]
> Если вы отсечките текущую запись, `Update` убедитесь, что вы сохраните изменения, позвонив в функцию участника, прежде чем перейти к другой записи. Если вы переходите на другую запись без обновления, ваши изменения теряются без предупреждения.

Использование одной из операций Поиска не `MoveFirst` `MoveNext`то же самое, как вызов или , однако, который просто делает первый или следующий ток записи без указания условия. Вы можете следить за операцией «Поиск» с помощью операции «Движение».

Имейте в виду следующее при использовании операций «Найти»:

- Если `Find` возврат ненулевой, текущая запись не определена. В этом случае необходимо переместить текущий указатель записи к действительной записи.

- Нельзя использовать операцию «Найти» с помощью набора записей типа моментального снимка только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты сша (месяц-день), даже если вы не используете американскую версию движка базы данных Microsoft Jet; в противном случае соответствующие записи могут не быть найдены.

- При работе с базами данных ODBC и большими динамитами вы можете обнаружить, что использование операций «Найти» происходит медленно, особенно при работе с большими рекордами. Вы можете повысить производительность, используя запросы с помощью индивидуальных **предложений ORDERBY** или **WHERE,** запросов параметров или `CDaoQuerydef` объектов, которые извлекают определенные индексированные записи.

Для получения соответствующей информации смотрите тему "Найтипервый, FindLast, FindNext, Найти Предыдущие методы" в Справке DAO.

## <a name="cdaorecordsetfindprev"></a><a name="findprev"></a>CDaoRecordset:FindPrev

Вызовите эту функцию участника, чтобы найти предыдущую запись, которая соответствует указанному условию.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строка выражения (например, **положение О ГДЕ** в заявлении S'L без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Функция `FindPrev` участника начинает свой поиск в текущей записи и выполняет поиск в обратном направлении к началу набора записей.

Если вы хотите включить все записи в поиск (а не только те, которые отвечают определенному состоянию) используйте одну из операций Move для перехода от записи к записи. Чтобы найти запись в наборе записей `Seek` типа таблицы, позвоните функции участника.

Если запись, соответствующая критериям, не находится, текущий указатель записи не определен и `FindPrev` возвращается ноль. Если запись содержит более одной записи, которая удовлетворяет критериям, `FindFirst` находит `FindNext` первое явление, находит следующее явление и так далее.

> [!CAUTION]
> Если вы отсечките текущую запись, `Update` убедитесь, что вы сохраните изменения, позвонив в функцию участника, прежде чем перейти к другой записи. Если вы переходите на другую запись без обновления, ваши изменения теряются без предупреждения.

Использование одной из операций Поиска не `MoveFirst` `MoveNext`то же самое, как вызов или , однако, который просто делает первый или следующий ток записи без указания условия. Вы можете следить за операцией «Поиск» с помощью операции «Движение».

Имейте в виду следующее при использовании операций «Найти»:

- Если `Find` возврат ненулевой, текущая запись не определена. В этом случае необходимо переместить текущий указатель записи к действительной записи.

- Нельзя использовать операцию «Найти» с помощью набора записей типа моментального снимка только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты сша (месяц-день), даже если вы не используете американскую версию движка базы данных Microsoft Jet; в противном случае соответствующие записи могут не быть найдены.

- При работе с базами данных ODBC и большими динамитами вы можете обнаружить, что использование операций «Найти» происходит медленно, особенно при работе с большими рекордами. Вы можете повысить производительность, используя запросы с помощью индивидуальных **предложений ORDERBY** или **WHERE,** запросов параметров или `CDaoQuerydef` объектов, которые извлекают определенные индексированные записи.

Для получения соответствующей информации смотрите тему "Найтипервый, FindLast, FindNext, Найти Предыдущие методы" в Справке DAO.

## <a name="cdaorecordsetgetabsoluteposition"></a><a name="getabsoluteposition"></a>CDaoRecordset::GetAbsolutePosition

Возвращает рекордное количество текущей записи объекта записи.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Возвращаемое значение

Целый ряд до количества записей в рекорде. Соответствует ординаторской позиции текущего рекорда в рекорде.

### <a name="remarks"></a>Remarks

Значение свойства AbsolutePosition базового объекта DAO на нулевой основе; установка 0 относится к первому рекорду в рекорде. Вы можете определить количество заполненных записей в рекорде, позвонив в [GetRecordCount.](#getrecordcount) Вызов `GetRecordCount` может занять некоторое время, поскольку он должен получить доступ ко всем записям, чтобы определить количество.

Если нет текущей записи, как, когда нет записей в рекорде, - 1 возвращается. Если текущая запись удалена, значение свойства AbsolutePosition не определено, и MFC бросает исключение, если на него ссылаются. Для записей типа динасета к концу последовательности добавляются новые записи.

> [!NOTE]
> Это свойство не предназначено для использования в качестве суррогатного рекордного числа. Закладки по-прежнему являются рекомендуемым способом сохранения и возвращения в заданную позицию и являются единственным способом размещения текущей записи во всех типах объектов записей. В частности, позиция данной записи изменяется при удалении записи(ы), предшествующей ей. Также нет уверенности в том, что данная запись будет иметь ту же абсолютную позицию, если запись будет повторно создана снова, потому что порядок отдельных записей в рекордном наборе не гарантируется, если он не создан с заявлением S'L с использованием оговорки **ORDERBY.**

> [!NOTE]
> Эта функция участника действительна только для записей типа динасета и моментального снимка.

Подробнее об этом читайте в теме "АбсолютПозиция Недвижимость" в справке DAO.

## <a name="cdaorecordsetgetbookmark"></a><a name="getbookmark"></a>CDaoRecordset::GetBookmark

Позвоните в эту функцию участника, чтобы получить значение закладки в определенной записи.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, представляющее закладку, на текущей записи.

### <a name="remarks"></a>Remarks

При создании или открытии объекта записи каждая из его записей уже имеет уникальную закладку, если она их поддерживает. Звоните, `CanBookmark` чтобы определить, поддерживает ли набор записей закладки.

Закладка можно сохранить для текущей записи, назначив значение `COleVariant` закладки объекту. Чтобы быстро вернуться к этой записи в любое время после перехода к другой записи, позвоните `SetBookmark` с параметром, соответствующим значению этого `COleVariant` объекта.

> [!NOTE]
> Вызов [повторного изменения](#requery) DAO закладки.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetcachesize"></a><a name="getcachesize"></a>CDaoRecordset::GetCacheSize

Вызовите эту функцию участника, чтобы получить количество кэшированных записей.

```
long GetCacheSize();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, окоторомывающее количество записей в наборе записей типа динасета, содержащего данные, локально кэшируются из источника данных ODBC.

### <a name="remarks"></a>Remarks

Кэширование данных повышает производительность приложения, которое получает данные с удаленного сервера через объекты записей типа динасета. Кэш — это пространство в локальной памяти, в мещавх данных, полученных с последнего времени с сервера, в случае, если данные будут запрошены снова во время работы приложения. При запросе данных движок базы данных Microsoft Jet сначала проверяет кэш для запрашиваемых данных, а не изыскает его с сервера, что занимает больше времени. Данные, не полученные из источника данных ODBC, не сохраняются в кэше.

Любой источник данных ODBC, например прилагаемая таблица, может иметь локальный кэш.

Для получения соответствующей информации смотрите тему "Кэш-Изгой, КэшСтарт Свойства" в Справке DAO.

## <a name="cdaorecordsetgetcachestart"></a><a name="getcachestart"></a>CDaoRecordset::GetCacheStart

Позвоните в эту функцию участника, чтобы получить значение закладки первой записи в наборе записей, которые будут кэшированы.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Возвращаемое значение

A, `COleVariant` который определяет закладку первой записи в рекорде, которая будет кэшироваться.

### <a name="remarks"></a>Remarks

Движок базы данных Microsoft Jet запрашивает записи в диапазоне кэша от кэша и запрашивает записи за пределами диапазона кэша с сервера.

> [!NOTE]
> Записи, извлеченные из кэша, не отражают изменений, внесенных одновременно с исходными данными другими пользователями.

Для получения соответствующей информации смотрите тему "Кэш-Изгой, КэшСтарт Свойства" в Справке DAO.

## <a name="cdaorecordsetgetcurrentindex"></a><a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex

Вызовите эту функцию участника, чтобы определить индекс, `CDaoRecordset` который в настоящее время используется в объекте индексированного типа таблицы.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Возвращаемое значение

Имя `CString` индекса, которое в настоящее время используется с рекордным набором типов таблицы. Возвращает пустую строку, если индекс не установлен.

### <a name="remarks"></a>Remarks

Этот индекс является основой для заказа записей в наборе записей типа таблицы и используется функцией участника [Seek](#seek) для поиска записей.

Объект `CDaoRecordset` может иметь более одного индекса, но может использовать только один индекс одновременно (хотя объект [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) может иметь несколько индексов, определенных на нем).

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetgetdatecreated"></a><a name="getdatecreated"></a>CDaoRecordset::GetDateCreated

Вызов ими функции участника для получения даты и времени создания базовой таблицы.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий дату и время создания базовой таблицы.

### <a name="remarks"></a>Remarks

Настройки даты и времени получены из компьютера, на котором была создана базовая таблица.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated

Вызовите эту функцию участника, чтобы получить дату и время последнего обновления схемы.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий дату и время последнего обновления базовой структуры таблицы (схема).

### <a name="remarks"></a>Remarks

Настройки даты и времени получены из компьютера, на котором в последний раз обновлялась базовая структура таблицы (схема).

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetdefaultdbname"></a><a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName

Вызовите эту функцию пользователя, чтобы определить имя базы данных для этого набора записей.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий путь и имя базы данных, из которой происходит этот рекорд.

### <a name="remarks"></a>Remarks

Если запись создается без указателя на [CDaoDatabase,](../../mfc/reference/cdaodatabase-class.md)то этот путь используется рекордным набором для открытия базы данных по умолчанию. По умолчанию эта функция возвращает пустую строку. Когда ClassWizard получает новый `CDaoRecordset`рекордет из, он создаст эту функцию для вас.

Следующий пример иллюстрирует использование двойной backslash ( )\\\\в строке, как это требуется для строки, которые будут интерпретироваться правильно.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

## <a name="cdaorecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CDaoRecordset::GetDefaultS

Платформа вызывает эту функцию участника, чтобы получить заявление по умолчанию, на котором основан освоен рекорд.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий выписку по умолчанию.

### <a name="remarks"></a>Remarks

Это может быть имя таблицы или выписка s'L **SELECT.**

Вы косвенно определяете заявление по умолчанию, объявляя класс записей с ClassWizard, и ClassWizard выполняет эту задачу за вас.

Если вы передаете нулевую строку S'L, чтобы [открыть,](#open)то эта функция называется для определения имени таблицы или S'L для вашего рекорда.

## <a name="cdaorecordsetgeteditmode"></a><a name="geteditmode"></a>CDaoRecordset::GetEditMode

Вызовите эту функцию участника, чтобы определить состояние редактирования, которое является одним из следующих значений:

```
short GetEditMode();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указывающее состояние редактирования для текущей записи.

### <a name="remarks"></a>Remarks

|Значение|Описание|
|-----------|-----------------|
|`dbEditNone`|Операция редактирования не выполняется.|
|`dbEditInProgress`|Был вызван метод `Edit`.|
|`dbEditAdd`|Был вызван метод `AddNew`.|

Для получения соответствующей информации смотрите тему "EditMode собственности" в DAO Help.

## <a name="cdaorecordsetgetfieldcount"></a><a name="getfieldcount"></a>CDaoRecordset::GetFieldCount

Вызовите эту функцию участника, чтобы получить количество полей (столбцов), определенных в наборе записей.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество полей в рекорде.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo

Позвоните этой функции участника для получения информации о полях в наборе записей.

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

*Nindex*<br/>
Индекс на нулевой основе предопределенного поля в коллекции полей рекорда для поиска по индексу.

*Fieldinfo*<br/>
Ссылка на структуру [CDaoFieldInfo.](../../mfc/reference/cdaofieldinfo-structure.md)

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию о записи для получения. Доступные варианты перечислены здесь вместе с тем, что они вызывают функцию возвращения. Для наилучшей производительности, получить только уровень информации, вам нужно:

- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, тип, размер, атрибуты

- `AFX_DAO_SECONDARY_INFO`Первичная информация, плюс: Обыденное положение, Обязательно, Разрешить нулевую длину, Коллажирование заказа, Иностранное имя, Поле источника, Таблица источника

- `AFX_DAO_ALL_INFO`Первичная и второстепенная информация, а также: Значение по умолчанию, Правило валидации, Текст валидации

*lpszName*<br/>
Имя поля.

### <a name="remarks"></a>Remarks

Одна из версий функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.

Для описания возвращенной информации [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) см. Эта структура имеет членов, которые соответствуют пунктам информации, перечисленных выше в описании *dwInfoOptions*. Когда вы запрашиваете информацию на одном уровне, вы получаете информацию для любых предыдущих уровней, а также.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaorecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CDaoRecordset::GetFieldValue

Вызов исчерпе эту функцию участника для извлечения данных в наборе записей.

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);

virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, содержащую имя поля.

*varValue*<br/>
Ссылка на `COleVariant` объект, который будет хранить значение поля.

*Nindex*<br/>
Индекс поля с нулевым уровнем в коллекции полей рекорда для поиска по индексу.

### <a name="return-value"></a>Возвращаемое значение

Две версии `GetFieldValue` этого возвращения значения возвращают объект [COleVariant,](../../mfc/reference/colevariant-class.md) содержащий значение поля.

### <a name="remarks"></a>Remarks

Вы можете посмотреть поле по имени или по ординаторному положению.

> [!NOTE]
> Более эффективно вызывать одну из версий этой функции-члена, которая использует ссылку `COleVariant` на объект `COleVariant` в качестве параметра, вместо того, чтобы вызывать версию, которая возвращает объект. Последние версии этой функции сохраняются для обратной совместимости.

Используйте `GetFieldValue` и [SetFieldValue](#setfieldvalue) динамически связывают поля во время выполнения, а не статически связывающие столбцы с помощью механизма [DoFieldExchange.](#dofieldexchange)

`GetFieldValue`и `DoFieldExchange` механизм может быть объединен для повышения производительности. Например, `GetFieldValue` используйте для получения значения, необходимого только по требованию, и присвоить этот вызов кнопке "Больше информации" в интерфейсе.

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetgetindexcount"></a><a name="getindexcount"></a>CDaoRecordset::GetIndexCount

Вызовите эту функцию участника, чтобы определить количество индексов, доступных на наборе записей типа таблицы.

```
short GetIndexCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество индексов в наборе записей типов таблицы.

### <a name="remarks"></a>Remarks

`GetIndexCount`полезно для циклирования всех индексов в наборе рекордов. Для этого используйте `GetIndexCount` совместно с [GetIndexInfo](#getindexinfo). Если вы называете эту функцию участника на записях типа динасета или моментального типа, MFC бросает исключение.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaorecordsetgetindexinfo"></a><a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo

Вызовите эту функцию участника для получения различного рода информации об индексе, определенном в базовой таблице, лежащем в основе набора записей.

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс с нулевым уровнем в коллекции индексов таблицы для поиска по числовому положению.

*индексинфо*<br/>
Ссылка на структуру [CDaoIndexInfo.](../../mfc/reference/cdaoindexinfo-structure.md)

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию об индексе для извлечения. Доступные варианты перечислены здесь вместе с тем, что они вызывают функцию возвращения. Для наилучшей производительности, получить только уровень информации, вам нужно:

- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, Полевая информация, Поля

- `AFX_DAO_SECONDARY_INFO`Первичная информация, а также: Первичная, Уникальная, Кластерная, Игнорируемые, Обязательные, Иностранные

- `AFX_DAO_ALL_INFO`Первичная и второстепенная информация, плюс: Отдельный граф

*lpszName*<br/>
Указатель на имя объекта индекса для поиска по имени.

### <a name="remarks"></a>Remarks

Одна из версий функции позволяет искать индекс по его положению в коллекции. Другая версия позволяет искать индекс по имени.

Для описания возвращенной информации [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) см. Эта структура имеет членов, которые соответствуют пунктам информации, перечисленных выше в описании *dwInfoOptions*. Когда вы запрашиваете информацию на одном уровне, вы получаете информацию для любых предыдущих уровней, а также.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaorecordsetgetlastmodifiedbookmark"></a><a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark

Позвоните в эту функцию участника, чтобы получить закладку последней добавленной или обновленной записи.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Содержит `COleVariant` закладку, указывают на недавно добавленную или измененную запись.

### <a name="remarks"></a>Remarks

При создании или открытии объекта записи каждая из его записей уже имеет уникальную закладку, если она их поддерживает. Позвоните [GetBookmark,](#getbookmark) чтобы определить, поддерживает ли набор записей закладки. Если рекорд не поддерживает закладки, он `CDaoException` брошен.

При добавлении записи она отображается в конце набора записей и не является текущей записью. Чтобы сделать новую `GetLastModifiedBookmark` запись текущей, позвоните, а затем позвоните, `SetBookmark` чтобы вернуться к недавно добавленной записи.

Для получения соответствующей информации смотрите тему "Последнее изменение собственности" в справке DAO.

## <a name="cdaorecordsetgetlockingmode"></a><a name="getlockingmode"></a>CDaoRecordset:GetLockingMode

Вызовите эту функцию участника, чтобы определить тип блокировки в силе для рекордных.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если тип блокировки пессимистично, в противном случае 0 для оптимистичной блокировки записи.

### <a name="remarks"></a>Remarks

Когда действует пессимистическая блокировка, страница данных, содержащая запись, которая используется, блокируется, как только вы называете функцию члена [Редактирования.](#edit) Страница разблокирована, когда вы звоните функции [участника обновления](#update) или [закрытия](#close) или любой из операций Move или Find.

При эффективной блокировке оптимистичной информации страница данных, содержащая запись, блокируется только во время обновления записи с функцией `Update` участника.

При работе с источниками данных ODBC режим блокировки всегда оптимистичен.

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetgetname"></a><a name="getname"></a>CDaoRecordset::GetName

Вызовите эту функцию участника, чтобы получить имя набора записей.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя `CString` рекорда.

### <a name="remarks"></a>Remarks

Название рекордсета должно начинаться с буквы и может содержать не более 40 символов. Он может включать в себя цифры и подчеркивать символы, но не может включать знаки препинания или пробелы.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetparamvalue"></a><a name="getparamvalue"></a>CDaoRecordset::GetParamValue

Вызов используйте эту функцию участника для получения текущего значения указанного параметра, хранящегося в базовом объекте DAOParameter.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Численное положение параметра в базовом объекте DAOParameter.

*lpszName*<br/>
Название параметра, значение которого вы хотите.

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant,](../../mfc/reference/colevariant-class.md) содержащий значение параметра.

### <a name="remarks"></a>Remarks

Вы можете получить доступ к параметру либо по имени, либо по его численному положению в коллекции.

Для получения соответствующей информации смотрите тему "Объект параметра" в справке DAO.

## <a name="cdaorecordsetgetpercentposition"></a><a name="getpercentposition"></a>CDaoRecordset::GetPercentPosition

При работе с динасетом типа или моментального типа `GetPercentPosition` recordset, если вы звоните перед полностью заполнения рекорда, количество движения по отношению к числу записей, доступ к которым, как указано по телефону [GetRecordCount](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>Возвращаемое значение

Число от 0 до 100, которое указывает приблизительное местоположение текущей записи в объекте записи на основе процента записей в наборе записей.

### <a name="remarks"></a>Remarks

Вы можете перейти к последней записи, позвонив [MoveLast](#movelast) для завершения популяции всех записей, но это может занять значительное количество времени.

Можно вызвать `GetPercentPosition` все три типа объектов регистрации, включая таблицы без индексов. Тем не менее, вы не можете вызвать `GetPercentPosition` снимки прокрутки только вперед или на наборе записей, открытых из сквозного запроса против внешней базы данных. Если нет текущей записи, или он текущая `CDaoException` запись была удалена, a брошен.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetrecordcount"></a><a name="getrecordcount"></a>CDaoRecordset::GetRecordCount

Позвоните в эту функцию участника, чтобы узнать, сколько записей в наборе записей было доступно.

```
long GetRecordCount();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей, доступных в объекте записи.

### <a name="remarks"></a>Remarks

`GetRecordCount`не указывает, сколько записей содержится в динасетном типе или наборе моментальных снимков до тех пор, пока не будут доступны все записи. Этот вызов функции члена может занять значительное количество времени.

После того, как последняя запись была доступна, значение возврата указывает общее количество неудаленных записей в записи. Чтобы заставить последнюю запись быть `MoveLast` доступной, позвоните функции или `FindLast` функции участника для записи. Вы также можете использовать s'L Count для определения приблизительного числа записей, которые будет возвращаться в ашего запрос.

По мере того, как приложение удаляет записи в наборе `GetRecordCount` записей типа динасета, значение возврата уменьшается. Однако записи, удаленные другими `GetRecordCount` пользователями, не отражаются до тех пор, пока текущая запись не будет помещаться в удаленную запись. Если вы выполняете транзакцию, которая влияет на количество `GetRecordCount` записей и впоследствии откатываете транзакцию, не будет отражать фактическое количество оставшихся записей.

Значение `GetRecordCount` из набора записей типа моментального снимка не зависит от изменений в базовых таблицах.

Значение `GetRecordCount` из набора записей типа таблицы отражает приблизительное количество записей в таблице и сразу же влияет на добавление и удаление записей таблицы.

Запись без записей возвращает значение 0. При работе с прикрепленными таблицами `GetRecordCount` или базами данных ODBC, всегда возвращается - 1. Вызов `Requery` функции участника на момент сбросе записи сбрасывает значение так же, `GetRecordCount` как если бы запрос был повторно выполнен.

Для получения соответствующей информации смотрите тему "RecordCount Property" в справке DAO.

## <a name="cdaorecordsetgetsql"></a><a name="getsql"></a>CDaoRecordset::GetS'L

Вызовите эту функцию участника, чтобы получить выписку по S'L, которая использовалась для выбора записей записей, когда он был открыт.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащая выписку по S'L.

### <a name="remarks"></a>Remarks

Как правило, это будет заявление S'L **SELECT.**

Строка, `GetSQL` которую возвращается, обычно отличается от любой строки, которую вы, возможно, перешли к набору записей в параметре *lpszS'L* функции [Open.](#open) Это происходит потому, что в наборе записей построена полная выписка по S'L, основанная на `Open`том, что вы передали, что вы указали в ClassWizard, и что вы, возможно, указали в [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) членов данных.

> [!NOTE]
> Вызов эту функцию `Open`участника только после вызова .

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgettype"></a><a name="gettype"></a>CDaoRecordset::GetType

Вызовите эту функцию участника после открытия набора записей, чтобы определить тип объекта записи.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений, указывающих на тип набора рекордов:

- `dbOpenTable`Запись типа таблицы

- `dbOpenDynaset`Рекордсмен типа динасета

- `dbOpenSnapshot`Запись типа моментального снимка

### <a name="remarks"></a>Remarks

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule

Вызовите эту функцию участника, чтобы определить правило, используемое для проверки данных.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий значение, проверяемое данными в записи при изменении или добавлении в таблицу.

### <a name="remarks"></a>Remarks

Это правило основано на тексте и применяется каждый раз при изменении основной таблицы. Если данные не являются законными, MFC бросает исключение. Возвращалось сообщение об ошибке — это текст свойства ВалидацииТекст основного полевого объекта, если указано, или текст выражения, указанного свойством ВалидацииПравило основного полевого объекта. Вы можете позвонить [в GetValidationText,](#getvalidationtext) чтобы получить текст сообщения об ошибке.

Например, поле в записи, требующее дня месяца, может иметь правило проверки, такое как "DAY BETWEEN 1 AND 31".

Для получения соответствующей информации, см.

## <a name="cdaorecordsetgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoRecordset::GetValidationText

Вызовите эту функцию участника, чтобы получить текст свойства ValidationText базового объекта поля.

```
CString GetValidationText();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий текст сообщения, отображаемый, если значение поля не соответствует правилу проверки базового объекта поля.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации смотрите тему "ValidationText Property" в справке DAO.

## <a name="cdaorecordsetisbof"></a><a name="isbof"></a>CDaoRecordset::IsBOF

Позвоните в эту функцию участника, прежде чем прокрутите от записи к записи, чтобы узнать, прошли ли вы до первой записи рекорда.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись не содержит записей или если вы прокрутили назад до первой записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы также `IsBOF` можете `IsEOF` позвонить вместе с определить, содержит ли запись какие-либо записи или он пуст. Сразу после `Open`вызова, если запись не `IsBOF` содержит записей, возвращается ненулевой. Когда вы открываете рекорд, который имеет по крайней мере `IsBOF` одну запись, первая запись — это текущая запись и возвращает 0.

Если первая запись текущей записи, и вы звоните, `MovePrev` `IsBOF` будет впоследствии вернуться ненулевой. Если `IsBOF` возвращается ненулевой и вы звоните, `MovePrev`исключение брошено. Если `IsBOF` возврат ненулевой, текущая запись не определена, и любое действие, требующее текущей записи, приведет к исключению.

Влияние конкретных методов на `IsBOF` и `IsEOF` настройки:

- Вызов `Open*` внутренне делает первую запись в записи `MoveFirst`текущей записи, позвонив . Поэтому призыв `Open` к пустому набору записей вызывает `IsBOF` и `IsEOF` возвращает ненулевой. (См. следующую таблицу `MoveFirst` для `MoveLast` поведения не удалось или вызова.)

- Все операции Move, которые успешно `IsBOF` `IsEOF` обнаруживать запись причиной как и вернуть 0.

- Вызов `AddNew` с последующим вызовом, `Update` который успешно `IsBOF` вставляет новую `IsEOF` запись, приведет к возврату 0, но только в том случае, если он уже незеро. Состояние `IsEOF` воли всегда остается неизменным. Как определено движком базы данных Microsoft Jet, текущий указатель записи пустого рекорда находится в конце файла, поэтому любая новая запись вставляется после текущей записи.

- Любой `Delete` вызов, даже если он удаляет только оставшиеся записи `IsBOF` из `IsEOF`рекорда, не изменит значение или .

В этой таблице показано, какие операции `IsBOF` /  `IsEOF`Move разрешены с различными комбинациями .

||MoveFirst, MoveLast|MovePrev,<br /><br /> Перемещение < 0|Перемещение 0|Movenext<br /><br /> Перемещение > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`Знено,<br /><br /> `IsEOF`=0|Разрешено|Исключение|Исключение|Разрешено|
|`IsBOF`=0,<br /><br /> `IsEOF`Знезеро|Разрешено|Разрешено|Исключение|Исключение|
|Оба ненулевых|Исключение|Исключение|Исключение|Исключение|
|Оба 0|Разрешено|Разрешено|Разрешено|Разрешено|

Разрешение операции Move не означает, что операция успешно обнаружит запись. Он просто указывает, что попытка выполнения указанной операции Перемещение разрешена и не будет генерировать исключение. Значение функций `IsBOF` `IsEOF` и функций участника может измениться в результате попытки перемещения.

Влияние операций Move, которые не обнаруживают запись на значение `IsBOF` и `IsEOF` параметры, отображается в следующей таблице.

||Isbof|Iseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ненулевой|Ненулевой|
|`Move` 0|Без изменения.|Без изменения.|
|`MovePrev`, `Move` < 0|Ненулевой|Без изменения.|
|`MoveNext`, `Move` > 0|Без изменения.|Ненулевой|

Подробнее об этом читайте в теме "BOF, EOF Properties" в Справке DAO.

## <a name="cdaorecordsetisdeleted"></a><a name="isdeleted"></a>CDaoRecordset::Удаление

Вызовите эту функцию участника, чтобы определить, была ли удалена текущая запись.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись расположена на удаленной записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Если вы прокрутите запись и `IsDeleted` возвращаете TRUE (nonzero), то вы должны прокрутить другую запись, прежде чем вы сможете выполнить любые другие операции записи.

> [!NOTE]
> Вам не нужно проверять удаленный статус для записей в моментальном снимке или записи типа таблицы. Поскольку записи не могут быть удалены из `IsDeleted`снимка, нет необходимости вызывать . Для записей типа таблицы удаленные записи фактически удаляются из набора записей. После удаления записи либо вами, другим пользователем, либо другим рекордным набором, вы не можете прокрутить обратно к этой записи. Поэтому звонить не `IsDeleted`нужно.

При удалении записи из динасета она удаляется из набора записей и не позволяет прокрутить его обратно к этой записи. Однако, если запись в динасеже удаляется либо другим пользователем, либо `IsDeleted` в другом наборе записей, основанных на той же таблице, вернет истину, когда вы позже прокрутите к этой записи.

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "Метод удаления", "Последнее изменение свойства" и "Свойство EditMode".

## <a name="cdaorecordsetiseof"></a><a name="iseof"></a>CDaoRecordset::IsEOF

Позвоните в эту функцию участника при прокрутке от записи к записи, чтобы узнать, вышли ли вы за рамки последней записи рекорда.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись не содержит записей или если вы прокрутили за пределами последней записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы также `IsEOF` можете позвонить, чтобы определить, содержит ли запись какие-либо записи или он пуст. Сразу после `Open`вызова, если запись не `IsEOF` содержит записей, возвращается ненулевой. Когда вы открываете рекорд, который имеет по крайней мере `IsEOF` одну запись, первая запись — это текущая запись и возвращает 0.

Если последняя запись — это текущая `IsEOF` запись при вызове, `MoveNext`то она впоследствии вернется ненулевой. Если `IsEOF` возвращается ненулевой и вы звоните, `MoveNext`исключение брошено. Если `IsEOF` возврат ненулевой, текущая запись не определена, и любое действие, требующее текущей записи, приведет к исключению.

Влияние конкретных методов на `IsBOF` и `IsEOF` настройки:

- Вызов `Open` внутренне делает первую запись в записи `MoveFirst`текущей записи, позвонив . Поэтому призыв `Open` к пустому набору записей вызывает `IsBOF` и `IsEOF` возвращает ненулевой. (См. следующую таблицу `MoveFirst` поведения неудачного вызова.)

- Все операции Move, которые успешно `IsBOF` `IsEOF` обнаруживать запись причиной как и вернуть 0.

- Вызов `AddNew` с последующим вызовом, `Update` который успешно `IsBOF` вставляет новую `IsEOF` запись, приведет к возврату 0, но только в том случае, если он уже незеро. Состояние `IsEOF` воли всегда остается неизменным. Как определено движком базы данных Microsoft Jet, текущий указатель записи пустого рекорда находится в конце файла, поэтому любая новая запись вставляется после текущей записи.

- Любой `Delete` вызов, даже если он удаляет только оставшиеся записи `IsBOF` из `IsEOF`рекорда, не изменит значение или .

В этой таблице показано, какие операции `IsBOF` /  `IsEOF`Move разрешены с различными комбинациями .

||MoveFirst, MoveLast|MovePrev,<br /><br /> Перемещение < 0|Перемещение 0|Movenext<br /><br /> Перемещение > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`Знено,<br /><br /> `IsEOF`=0|Разрешено|Исключение|Исключение|Разрешено|
|`IsBOF`=0,<br /><br /> `IsEOF`Знезеро|Разрешено|Разрешено|Исключение|Исключение|
|Оба ненулевых|Исключение|Исключение|Исключение|Исключение|
|Оба 0|Разрешено|Разрешено|Разрешено|Разрешено|

Разрешение операции Move не означает, что операция успешно обнаружит запись. Он просто указывает, что попытка выполнения указанной операции Перемещение разрешена и не будет генерировать исключение. Значение функций `IsBOF` `IsEOF` и функций участника может измениться в результате попытки перемещения.

Влияние операций Move, которые не обнаруживают запись на значение `IsBOF` и `IsEOF` параметры, отображается в следующей таблице.

||Isbof|Iseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ненулевой|Ненулевой|
|`Move` 0|Без изменения.|Без изменения.|
|`MovePrev`, `Move` < 0|Ненулевой|Без изменения.|
|`MoveNext`, `Move` > 0|Без изменения.|Ненулевой|

Подробнее об этом читайте в теме "BOF, EOF Properties" в Справке DAO.

## <a name="cdaorecordsetisfielddirty"></a><a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty

Вызовите эту функцию участника, чтобы определить, был ли указанный член данных поля динасета помечен как "грязный" (изменен).

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, является ли какое-либо из полей грязным.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный член данных поля помечен как грязный; в противном случае 0.

### <a name="remarks"></a>Remarks

Данные во всех грязных полевых данных будут переданы в запись источника данных, когда текущая запись `Edit` `AddNew`обновляется вызовом к функции `Update` `CDaoRecordset` члена (после вызова или ). С помощью этих знаний можно предпринять дальнейшие шаги, такие как неудержимое использование члена данных поля для обозначения столбца, чтобы он не был записан на источник данных.

`IsFieldDirty`реализуется `DoFieldExchange`через .

## <a name="cdaorecordsetisfieldnull"></a><a name="isfieldnull"></a>CDaoRecordset::IsFieldNull

Вызовите эту функцию участника, чтобы определить, был ли указанный полевой член данных набора записей помечен как Null.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, является ли какое-либо из полей null.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный член данных поля помечен как Null; в противном случае 0.

### <a name="remarks"></a>Remarks

(В терминологии базы данных Null означает «не имеющий ценности» и не является таким же, как NULL в СЗ.) Если участник полевых данных помечен как Null, он интерпретируется как столбец текущей записи, для которого нет значения.

> [!NOTE]
> В некоторых `IsFieldNull` ситуациях использование может быть неэффективным, так как следующий пример кода иллюстрирует:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
> Если вы используете динамическую привязку `CDaoRecordset`записи, не вытекая из, не забудьте использовать VT_NULL, как показано в примере.

## <a name="cdaorecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable

Вызовите эту функцию участника, чтобы определить, является ли указанный участник данных поля «недействительным» (может быть установлен на значение Null; СЗ НУЛЛ не то же самое, что Null, что, в терминологии базы данных, означает "не имеет значения").

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, является ли какое-либо из полей null.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный член данных поля может быть сделан Null; в противном случае 0.

### <a name="remarks"></a>Remarks

Поле, которое не может быть null, должно иметь значение. Если вы попытаетесь установить такое поле для Null при добавлении или обновлении записи, источник данных отклоняет добавление или обновление и `Update` выбрасывает исключение. Исключение происходит при `Update`вызове, а `SetFieldNull`не при вызове.

## <a name="cdaorecordsetisopen"></a><a name="isopen"></a>CDaoRecordset::IsOpen

Вызовите эту функцию участника, чтобы определить, открыт ли набор записей.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция объекта `Open` `Requery` записи или члена ранее была вызвана и запись не была закрыта; в противном случае 0.

### <a name="remarks"></a>Remarks

## <a name="cdaorecordsetm_bcheckcachefordirtyfields"></a><a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset::m_bCheckCacheForDirtyFields

Содержит флаг, указывающий, автоматически ли кэшированные поля помечаются как грязные (измененные) и null.

### <a name="remarks"></a>Remarks

Флаг по умолчанию TRUE. Настройка в этом элементе данных контролирует весь механизм двойного буферизации. Если вы установите флаг на ИСТИНу, вы можете отключить кэширование на поле за полем основе с помощью механизма DFX. Если вы установите флаг FALSE, `SetFieldDirty` `SetFieldNull` вы должны позвонить и себя.

Установите этот член `Open`данных перед вызовом . Этот механизм предназначен главным образом для простоты использования. Производительность может быть более медленной из-за двойного буферизации полей по мере внесения изменений.

## <a name="cdaorecordsetm_nfields"></a><a name="m_nfields"></a>CDaoRecordset::m_nFields

Содержит количество полевых данных в классе recordset и количество столбцов, выбранных рекордным набором из источника данных.

### <a name="remarks"></a>Remarks

Конструктор для класса recordset должен `m_nFields` инициализировать с правильным числом статично связанных полей. ClassWizard пишет эту инициализацию для вас, когда вы используете его, чтобы объявить свой класс рекордсета. Вы также можете написать его вручную.

Платформа использует это число для управления взаимодействием между членами данных на местах и соответствующими столбцов текущей записи источника данных.

> [!NOTE]
> Это число должно соответствовать количеству выходных столбцов, зарегистрированных после `DoFieldExchange` вызова `SetFieldType` с параметром. `CDaoFieldExchange::outputColumn`

Вы можете связывать столбцы динамически путем `CDaoRecordset::GetFieldValue` и `CDaoRecordset::SetFieldValue`. Если вы это сделаете, вам не нужно `m_nFields` приравнять подсчет, чтобы `DoFieldExchange` отразить количество вызовов функции DFX в функции вашего члена функции.

## <a name="cdaorecordsetm_nparams"></a><a name="m_nparams"></a>CDaoRecordset::m_nParams

Содержит количество параметров данных в классе recordset - количество параметров, пройдено с запросом записи.

### <a name="remarks"></a>Remarks

Если в классе записей есть какие-либо параметры данных, конструктор для класса должен инициализировать *m_nParams* с правильным числом. Значение *m_nParams* по умолчанию до 0. Если вы добавляете параметры данных членов - что вы должны сделать вручную - вы также должны вручную добавить инициализацию в класс конструктора, чтобы отразить количество параметров (которые должны быть по крайней мере, как большой, как число "" заполнителей в *m_strFilter* или *m_strSort* строки).

Платформа использует это число, когда параметризирует запрос набора записей.

> [!NOTE]
> Этот номер должен соответствовать количеству "парамов", `SetFieldType` зарегистрированным `CFieldExchange::param`после `DoFieldExchange` звонка по параметру.

Для получения соответствующей информации смотрите тему "Объект параметра" в справке DAO.

## <a name="cdaorecordsetm_pdaorecordset"></a><a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset

Содержит указатель на интерфейс OLE для объекта daO `CDaoRecordset` recordset, лежащего в основе объекта.

### <a name="remarks"></a>Remarks

Используйте этот указатель, если вам нужно получить доступ к интерфейсу DAO напрямую.

Для получения соответствующей информации смотрите тему "Объект звукозаписи" в справке DAO.

## <a name="cdaorecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase

Содержит указатель на `CDaoDatabase` объект, через который запись подключена к источнику данных.

### <a name="remarks"></a>Remarks

Эта переменная устанавливается двумя способами. Как правило, при построении `CDaoDatabase` объекта записи указатель передается на уже открытый объект. Если вы передаете `CDaoRecordset` NULL `CDaoDatabase` вместо этого, создает объект для вас и открывает его. В любом `CDaoRecordset` случае хранит указатель в этой переменной.

Обычно вам не нужно будет напрямую `m_pDatabase`использовать указатель, хранящийся в. Если вы пишете свои `CDaoRecordset`собственные расширения, однако, возможно, потребуется использовать указатель. Например, вам может понадобиться указатель, `CDaoException`если вы бросаете свой собственный (ы).

Для получения соответствующей информации смотрите тему "Объект базы данных" в справке DAO.

## <a name="cdaorecordsetm_strfilter"></a><a name="m_strfilter"></a>CDaoRecordset::m_strFilter

Содержит строку, используемую для построения пункта **WHERE** оператора S'L.

### <a name="remarks"></a>Remarks

Он не включает в себя зарезервированное слово **WHERE** для фильтрации набора записей. Использование этого участника данных не применимо к записям типов таблицы. Использование не `m_strFilter` имеет никакого эффекта при `CDaoQueryDef` открытии набора записей с помощью указателя.

Используйте формат даты США (месячный день-год), когда фильтруется поля, содержащие даты, даже если вы не используете американскую версию движка базы данных Microsoft Jet; в противном случае данные могут быть отфильтрочены не так, как вы ожидаете.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetm_strsort"></a><a name="m_strsort"></a>CDaoRecordset::m_strSort

Содержит строку, содержащую оговорку **ORDERBY** выписки s-L без зарезервированных слов **ORDERBY.**

### <a name="remarks"></a>Remarks

Вы можете сортировать на объектах записи динасета и моментального типа.

Нельзя сортировать объекты записи типа таблицы. Чтобы определить порядок записи типа таблицы, позвоните [SetCurrentIndex.](#setcurrentindex)

Использование *m_strSort* не имеет никакого эффекта при `CDaoQueryDef` открытии набора записей с помощью указателя.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetmove"></a><a name="move"></a>CDaoRecordset::Движение

Вызовите эту функцию участника для размещения записей lRows из текущей *записи.*

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Параметры

*lRows*<br/>
Количество записей для перемещения вперед или назад. Положительные значения движутся вперед, к концу рекорда. Отрицательные значения движутся назад, к началу.

### <a name="remarks"></a>Remarks

Вы можете двигаться вперед или назад. `Move( 1 )``MoveNext`эквивалентно, и `Move( -1 )` эквивалентно `MovePrev`.

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Как правило, `IsBOF` звоните как до операции Move, так и `IsEOF` перед операцией Move, чтобы определить, есть ли записи. После того, `Requery`как `IsBOF` вы `IsEOF`позвоните `Open` или , позвоните либо или .

> [!NOTE]
> Если вы прокрутили мимо начала или конца `IsBOF` `IsEOF` рекорда (или возвращается ненулевой), вызов `Move` бросает . `CDaoException`

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

При вызове `Move` снимка прокрутки только вперед параметр *lRows* должен быть положительным рядом, а закладки не допускаются, поэтому вы можете двигаться только вперед.

Чтобы сделать первую, последнюю, следующую или предыдущую запись `MoveFirst` `MoveLast`в `MoveNext`записи текущей записи, позвоните в функцию , или `MovePrev` функцию участника.

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetmovefirst"></a><a name="movefirst"></a>CDaoRecordset::MoveFirst

Вызовите эту функцию участника, чтобы сделать первую запись в записи (если таковая имеется) текущей записи.

```
void MoveFirst();
```

### <a name="remarks"></a>Remarks

Вам не нужно `MoveFirst` звонить сразу после открытия набора записей. В это время первая запись (если таковая имеется) автоматически является текущей записью.

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Как правило, `IsBOF` звоните как до операции Move, так и `IsEOF` перед операцией Move, чтобы определить, есть ли записи. После того, `Requery`как `IsBOF` вы `IsEOF`позвоните `Open` или , позвоните либо или .

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Используйте `Move` функции для перехода от записи к записи, не применяя условия. Используйте операции «Поиск» для обнаружения записей в объекте записи типа динасета или моментального снимка, удовлетворяющих определенным состояниям. Чтобы найти запись в объекте рекорда `Seek`типа таблицы, позвоните.

Если набор записей относится к рекорду типа таблицы, движение следует за текущим индексом таблицы. Текущий индекс можно установить с помощью свойства индекса базового объекта DAO. Если вы не установите текущий индекс, порядок возврата записей не определен.

Если вы `MoveLast` звоните на объект записи на основе запроса или запроса S'L, запрос вынужден завершить, и объект записи полностью заселен.

Вы не `MoveFirst` можете `MovePrev` вызвать функцию или функцию участника с моментальным снимком прокрутки только вперед.

Для перемещения положения текущей записи в объекте записи определенное `Move`количество записей вперед или назад, позвоните в список .

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetmovelast"></a><a name="movelast"></a>CDaoRecordset::MoveLast

Вызовите эту функцию участника, чтобы сделать последнюю запись (если таковая имеется) в записи текущей записи.

```
void MoveLast();
```

### <a name="remarks"></a>Remarks

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Как правило, `IsBOF` звоните как до операции Move, так и `IsEOF` перед операцией Move, чтобы определить, есть ли записи. После того, `Requery`как `IsBOF` вы `IsEOF`позвоните `Open` или , позвоните либо или .

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Используйте `Move` функции для перехода от записи к записи, не применяя условия. Используйте операции «Поиск» для обнаружения записей в объекте записи типа динасета или моментального снимка, удовлетворяющих определенным состояниям. Чтобы найти запись в объекте рекорда `Seek`типа таблицы, позвоните.

Если набор записей относится к рекорду типа таблицы, движение следует за текущим индексом таблицы. Текущий индекс можно установить с помощью свойства индекса базового объекта DAO. Если вы не установите текущий индекс, порядок возврата записей не определен.

Если вы `MoveLast` звоните на объект записи на основе запроса или запроса S'L, запрос вынужден завершить, и объект записи полностью заселен.

Для перемещения положения текущей записи в объекте записи определенное `Move`количество записей вперед или назад, позвоните в список .

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetmovenext"></a><a name="movenext"></a>CDaoRecordset::MoveNext

Вызовите эту функцию участника, чтобы сделать следующую запись в записи текущей записи.

```
void MoveNext();
```

### <a name="remarks"></a>Remarks

Рекомендуется звонить `IsBOF` перед попыткой перейти к предыдущей записи. Вызов `MovePrev` будет бросать, `CDaoException` `IsBOF` если возвращает ненулевой, указывая либо, что вы уже прокрутили до первой записи или что никакие записи не были выбраны рекордом.

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Как правило, `IsBOF` звоните как до операции Move, так и `IsEOF` перед операцией Move, чтобы определить, есть ли записи. После того, `Requery`как `IsBOF` вы `IsEOF`позвоните `Open` или , позвоните либо или .

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Используйте `Move` функции для перехода от записи к записи, не применяя условия. Используйте операции «Поиск» для обнаружения записей в объекте записи типа динасета или моментального снимка, удовлетворяющих определенным состояниям. Чтобы найти запись в объекте рекорда `Seek`типа таблицы, позвоните.

Если набор записей относится к рекорду типа таблицы, движение следует за текущим индексом таблицы. Текущий индекс можно установить с помощью свойства индекса базового объекта DAO. Если вы не установите текущий индекс, порядок возврата записей не определен.

Для перемещения положения текущей записи в объекте записи определенное `Move`количество записей вперед или назад, позвоните в список .

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetmoveprev"></a><a name="moveprev"></a>CDaoRecordset::MovePrev

Вызовите эту функцию участника, чтобы сделать предыдущую запись в записи текущей записи.

```
void MovePrev();
```

### <a name="remarks"></a>Remarks

Рекомендуется звонить `IsBOF` перед попыткой перейти к предыдущей записи. Вызов `MovePrev` будет бросать, `CDaoException` `IsBOF` если возвращает ненулевой, указывая либо, что вы уже прокрутили до первой записи или что никакие записи не были выбраны рекордом.

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Как правило, `IsBOF` звоните как до операции Move, так и `IsEOF` перед операцией Move, чтобы определить, есть ли записи. После того, `Requery`как `IsBOF` вы `IsEOF`позвоните `Open` или , позвоните либо или .

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Используйте `Move` функции для перехода от записи к записи, не применяя условия. Используйте операции «Поиск» для обнаружения записей в объекте записи типа динасета или моментального снимка, удовлетворяющих определенным состояниям. Чтобы найти запись в объекте рекорда `Seek`типа таблицы, позвоните.

Если набор записей относится к рекорду типа таблицы, движение следует за текущим индексом таблицы. Текущий индекс можно установить с помощью свойства индекса базового объекта DAO. Если вы не установите текущий индекс, порядок возврата записей не определен.

Вы не `MoveFirst` можете `MovePrev` вызвать функцию или функцию участника с моментальным снимком прокрутки только вперед.

Для перемещения положения текущей записи в объекте записи определенное `Move`количество записей вперед или назад, позвоните в список .

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetopen"></a><a name="open"></a>CDaoRecordset::Открыто

Вы должны вызвать эту функцию участника, чтобы получить записи для записи.

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);

virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);

virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>Параметры

*nOpenType*<br/>
Одно из следующих значений:

- `dbOpenDynaset`Рекордсет динасетного типа с двунаправленной прокруткой. Это значение по умолчанию.

- `dbOpenTable`Запись типа таблицы с двунаправленной прокруткой.

- `dbOpenSnapshot`Запись типа моментального снимка с двунаправленной прокруткой.

*lpszS'L*<br/>
Строка указатель, содержащий один из следующих:

- Указатель NULL.

- Название одного или нескольких таблиц и/или querydefs (запятой-разделенных).

- Заявление S'L **SELECT** (по желанию с оговоркой S'L **WHERE** или **ORDERBY).**

- Сквозной запрос.

*nВарианты*<br/>
Один или несколько вариантов, перечисленных ниже. Значение по умолчанию — 0. Возможны следующие значения:

- `dbAppendOnly`Вы можете только приложить новые записи (динасет типа записи только). Этот параметр означает буквально, что записи могут быть только приложена. Классы баз данных MFC ODBC имеют опцию только для приложений, которая позволяет извлекать и пригорать к записям.

- `dbForwardOnly`Запись представляет собой снимок прокрутки только вперед.

- `dbSeeChanges`Создайте исключение, если другой пользователь изменяет редактируемую базу данных.

- `dbDenyWrite`Другие пользователи не могут изменять или добавлять записи.

- `dbDenyRead`Другие пользователи не могут просматривать записи (только запись типа таблицы).

- `dbReadOnly`Вы можете просматривать только записи; другие пользователи могут изменить их.

- `dbInconsistent`Допускается несогласованное обновление (только запись динасетного типа).

- `dbConsistent`Допускаются только последовательные обновления (только запись динасетного типа).

> [!NOTE]
> `dbConsistent` Константы `dbInconsistent` и являются взаимоисключающими. Вы можете использовать один или другой, но не `Open`оба в данном случае .

*pTableDef*<br/>
Указатель на объект [CDaoTableDef.](../../mfc/reference/cdaotabledef-class.md) Эта версия действительна только для записей типов таблицы. При использовании этой `CDaoDatabase` опции указатель, используемый для построения `CDaoRecordset` не используется; скорее, используется база данных, в которой находится таблица.

*p-КериДеф*<br/>
Указатель на объект [CDao-КуэриДеф.](../../mfc/reference/cdaoquerydef-class.md) Эта версия действительна только для записей типа динасета и моментального снимка. При использовании этой `CDaoDatabase` опции указатель, используемый для построения `CDaoRecordset` не используется; скорее, используется база данных, в которой находится запрос.

### <a name="remarks"></a>Remarks

Перед `Open`вызовом необходимо построить объект, установленный записью. Для этого можно использовать следующие способы.

- При построении объекта, установленного записи, передайте указатель объекту, `CDaoDatabase` который уже открыт.

- При построении объекта, установленного записи, передайте указатель объекту, `CDaoDatabase` который не открыт. Запись открывает `CDaoDatabase` объект, но не закрывает его при закрытии объекта записи.

- При построении объекта регистрации передайте указатель NULL. Объект записи `GetDefaultDBName` требует получить имя Microsoft Access. Файл MDB для открытия. Затем запись открывает `CDaoDatabase` объект и сохраняет его открытым до тех пор, пока запись открыта. При вызове `Close` на набор `CDaoDatabase` записей объект также закрывается.

    > [!NOTE]
    >  Когда набор записей `CDaoDatabase` открывает объект, он открывает источник данных с неэксклюзивным доступом.

Для версии, `Open` которая использует параметр *lpszS'L,* как только запись открыта, вы можете получить записи одним из нескольких способов. Первый вариант заключается в том, чтобы иметь функции DFX в вашем `DoFieldExchange`. Второй вариант заключается в использовании `GetFieldValue` динамической привязки, вызывая функцию члена. Эти опции могут быть реализованы отдельно или в комбинации. Если они объединены, вам придется пройти в выписке `Open`s'L самостоятельно по вызову .

При использовании второй `Open` версии того, `CDaoTableDef` где вы проходите в объекте, `DoFieldExchange` полученные столбцы будут доступны для вас, чтобы связать через и механизм DFX, и / или связывать динамически через `GetFieldValue`.

> [!NOTE]
> Вы можете `Open` звонить `CDaoTableDef` только с помощью объекта для записей типов таблицы.

Когда вы используете `Open` третью версию `CDaoQueryDef` того, где вы проходите в объекте, этот запрос будет `DoFieldExchange` выполнен, и полученные столбцы будут `GetFieldValue`доступны для вас, чтобы связать через и механизм DFX, и / или связывать динамически через .

> [!NOTE]
> Вы можете `Open` звонить `CDaoQueryDef` только с помощью объекта для записей типа динасета и моментального снимка.

Для первой версии, `Open` `lpszSQL` в которых используется параметр, записи выбираются на основе критериев, показанных в следующей таблице.

|Значение параметра `lpszSQL`|Выбранные записи определяются|Пример|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Строка возвращается . `GetDefaultSQL`||
|Запятый разделенный список одного или нескольких имен таблици и/или запроса.|Все столбцы, представленные `DoFieldExchange`в .|`"Customer"`|
|**Выберите** список столбцов **из** списка таблиц|Указанные столбцы из указанной таблицыdef (ы) и/или querydef(ы).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Обычная процедура заключается `Open`в том, чтобы пройти NULL к ; в этом `Open` случае `GetDefaultSQL`вызовы, переизданная функция члена, `CDaoRecordset`которую генерирует ClassWizard при создании класса, полученного. Это значение дает имя таблицы def (ы) и/или имя querydef (ы), указанное в ClassWizard. Вместо этого можно указать другую информацию в параметре *lpszS'L.*

Что бы `Open` вы ни прошли, конструируется окончательная строка S'L для запроса (строка может иметь положения S'L **WHERE** и **ORDERBY,** приложенные к строке *lpszS'L,* которую вы прошли), а затем выполняет запрос. Вы можете изучить построенную `GetSQL` строку, позвонив после вызова `Open`.

Члены полевых данных класса записей привязаны к выбранным столбцов. При возврате каких-либо записей первая запись становится текущей записью.

Если вы хотите установить параметры для набора записей, `m_strSort` такие `m_strFilter` как фильтр или сортировка, установите или после того, как вы построите объект записи, но до `Open`вызова. Если вы хотите обновить записи в записи после того, `Requery`как запись уже открыта, позвоните .

Если вы `Open` вызываете запись типа динассета или моментального снимка, или если источник данных относится к выписке `dbOpenTable` s-L или таблице, представляющей прилагаемую таблицу, вы не можете использовать для аргумента типа; если вы делаете, MFC бросает исключение. Чтобы определить, представляет ли объект таблицы прилагаемую таблицу, создайте объект [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) и позвоните в функцию члена [GetConnect.](../../mfc/reference/cdaotabledef-class.md#getconnect)

Используйте `dbSeeChanges` флаг, если вы хотите улавливать изменения, внесенные другим пользователем или другой программой на вашей машине, когда вы редактируете или удаляете ту же запись. Например, если два пользователя начинают редактировать одну и `Update` ту же запись, первый пользователь, позвонивший функции участника, преуспевает. Когда `Update` вызывается вторым пользователем, a `CDaoException` брошен. Аналогичным образом, если второй `Delete` пользователь пытается вызвать, чтобы удалить запись, и `CDaoException` она уже была изменена первым пользователем, происходит.

Обычно, если пользователь `CDaoException` получает это во время обновления, код должен обновить содержимое полей и получить вновь измененные значения. Если в процессе исключения происходит исключение, код может отображать пользователю новые данные записи и сообщение о том, что данные недавно изменились. На этом код может запросить подтверждение того, что пользователь по-прежнему хочет удалить запись.

> [!TIP]
> Используйте опцию прокрутки только вперед ()`dbForwardOnly`для повышения производительности, когда приложение делает один проход через набор записей, открытый из источника данных ODBC.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetrequery"></a><a name="requery"></a>CDaoRecordset::Requery

Вызов ими функции участника для восстановления (обновления) набора записей.

```
virtual void Requery();
```

### <a name="remarks"></a>Remarks

При возврате каких-либо записей первая запись становится текущей записью.

Для того, чтобы запись отражала дополнения и удаления, которые вы или другие пользователи вносите в исходный исход данных, необходимо восстановить набор записей, позвонив в систему. `Requery` Если запись — это динасет, он автоматически отражает обновления, которые вы или другие пользователи вносили в существующие записи (но не дополнения). Если запись представляет собой моментальный `Requery` снимок, необходимо позвонить, чтобы отразить edits другими пользователями, а также дополнения и удаления.

Для динасета или снимка `Requery` звоните в любое время, когда вы хотите восстановить набор записей с помощью значений параметров. Установите новый фильтр или сортируйте, установив [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) перед вызовом. `Requery` Установите новые параметры, назначив новые значения `Requery`членам параметров, прежде чем вызывать.

Если попытка восстановить набор записей завершается неудачей, запись закрывается. Перед вызовом `Requery`можно определить, можно ли перезадействовать запись, позвонив в функцию участника [CanRestart.](#canrestart) `CanRestart`не гарантирует, `Requery` что это удастся.

> [!CAUTION]
> Звоните `Requery` только после `Open`того, как вы позвонили .

> [!NOTE]
> Вызов [повторного изменения](#requery) DAO закладки.

Вы не можете `Requery` вызвать запись типа динасета или `CanRestart` моментального снимка, если вызов возвращает сярприз 0, и вы не можете использовать его на записи типа таблицы.

Если `IsBOF` оба `IsEOF` и возврат ненулевой после вызова, `Requery`запрос не возвращает никаких записей и запись не будет содержать данные.

Для получения соответствующей информации смотрите тему "Метод повторного действия" в справке DAO.

## <a name="cdaorecordsetseek"></a><a name="seek"></a>CDaoRecordset::Ищите

Вызовите эту функцию участника, чтобы найти запись в объекте рекордного набора индексированного типа таблицы, который удовлетворяет указанным критериям для текущего индекса, и сделайте эту запись текущей записью.

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);

BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>Параметры

*lpsz Сравнение*<br/>
Одно из следующих выражений строки:\<"<", "к", "к", ">" или ">".

*pKey1*<br/>
Указатель на [COleVariant,](../../mfc/reference/colevariant-class.md) значение которого соответствует первому полю в индексе. Обязательный элемент.

*pKey2*<br/>
Указатель на `COleVariant` значение, значение которого соответствует второму полю в индексе, если таковое имеется. По умолчанию к NULL.

*pKey3*<br/>
Указатель на `COleVariant` значение, значение которого соответствует третьему полю в индексе, если таковое имеется. По умолчанию к NULL.

*pKeyArray*<br/>
Указатель на массив вариантов. Размер массива соответствует количеству полей в индексе.

*nKeys*<br/>
Целый размер массива, который является числом полей в индексе.

> [!NOTE]
> Не указывая подстановочные знаки в ключах. Wildcards заставит `Seek` вернуть не соответствующие записи.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соответствующие записи найдены, в противном случае 0.

### <a name="remarks"></a>Remarks

Используйте вторую (массивную) `Seek` версию для обработки индексов четырех или более областей.

`Seek`позволяет осуществлять поиск высокопроизводительных индексов на рекордных наборах таблиц. Вы должны установить текущий индекс, позвонив `SetCurrentIndex` перед вызовом. `Seek` Если индекс определяет неоднозначное ключевое `Seek` поле или поля, находит первую запись, которая удовлетворяет критериям. Если вы не установите индекс, будет брошено исключение.

Обратите внимание, что если вы не создаете набор записей UNICODE, `COleVariant` объекты должны быть явно объявлены ANSI. Это может быть сделано с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `VT_BSTRT` `COleVariant` **,** *(lpszSrc* , *vtSrc* **)** форма конструктора с *vtSrc* набор (ANSI) или с помощью функции [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *(lpszSrc* **,** *vtSrc* **)** с *vtSrc* установить на .**(**

При вызове, `Seek`вы передаете одну или несколько ключевых значений и оператор сравнения ("<", "з",\<"к", ">" или ">"). `Seek`поиск по указанным ключевым полям и находит первую запись, которая удовлетворяет критериям, указанным *lpszComparison* и *pKey1*. После того, как найдено, `Seek` возвращает сяков, и делает, что запись тока. Если `Seek` не удается `Seek` найти совпадение, возвращаетнулнул нулю, и текущая запись не определена. При непосредственном использовании DAO необходимо явно проверить свойство NoMatch.

Если `lpszComparison` это "к", ">" или ">", `Seek` начинается в начале индекса. Если *lpszComparison* является "<" или `Seek` "<", начинается в конце индекса и ищет назад, если есть дубликаты индексных записей в конце. В этом `Seek` случае начинается с произвольного входа среди дублирующихся записей индекса в конце индекса.

При использовании `Seek`не требуется фиксироваться.

Чтобы найти запись в динасетном типе или наборе моментальных снимков, удовлетворяет определенному условию, используйте операции Поиска. Чтобы включить все записи, а не только те, которые удовлетворяют определенному условию, используйте операции Move для перехода от записи к записи.

Вы не `Seek` можете вызвать прикрепленную таблицу любого типа, потому что прилагаемые таблицы должны быть открыты как динасет типа или моментальные записи типа. Однако, если `CDaoDatabase::Open` вы позвоните, чтобы непосредственно открыть `Seek` установленную базу данных ISAM, вы можете вызвать таблицы в этой базе данных, хотя производительность может быть медленной.

Для получения соответствующей информации, см.

## <a name="cdaorecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition

Устанавливает относительное рекордное число текущего рекорда объекта записи.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Параметры

*lПозиция*<br/>
Соответствует ординаторской позиции текущего рекорда в рекорде.

### <a name="remarks"></a>Remarks

Вызов `SetAbsolutePosition` позволяет позиционировать текущий указатель записи к определенной записи, основанной на его ординативном положении в динасетном типе или наборе моментальных снимков. Вы также можете определить текущий номер записи, [позвонив в GetAbsolutePosition.](#getabsoluteposition)

> [!NOTE]
> Эта функция участника действительна только для записей типа динасета и моментального снимка.

Значение свойства AbsolutePosition базового объекта DAO на нулевой основе; установка 0 относится к первому рекорду в рекорде. Установка значения, превышающее количество заполненных записей, заставляет MFC выбросить исключение. Количество заполненных записей можно определить, позвонив в функцию `GetRecordCount` участника.

Если текущая запись удалена, значение свойства AbsolutePosition не определено, и MFC бросает исключение, если на него ссылаются. Новые записи добавляются к концу последовательности.

> [!NOTE]
> Это свойство не предназначено для использования в качестве суррогатного рекордного числа. Закладки по-прежнему являются рекомендуемым способом сохранения и возвращения в заданную позицию и являются единственным способом позиционирования текущей записи во всех типах объектов регистрации, поддерживающих закладки. В частности, позиция данной записи изменяется при удалении записи(ы), предшествующей ей. Также нет уверенности в том, что данная запись будет иметь ту же абсолютную позицию, если запись будет повторно создана снова, потому что порядок отдельных записей в рекордном наборе не гарантируется, если он не создан с заявлением S'L с использованием оговорки **ORDERBY.**

Подробнее об этом читайте в теме "АбсолютПозиция Недвижимость" в справке DAO.

## <a name="cdaorecordsetsetbookmark"></a><a name="setbookmark"></a>CDaoRecordset::SetBookmark

Позвоните этой функции участника, чтобы позиционировать запись в записи, содержащей указанную закладку.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Объект [COleVariant,](../../mfc/reference/colevariant-class.md) содержащий значение закладки для конкретной записи.

### <a name="remarks"></a>Remarks

При создании или открытии объекта записи каждая из его записей уже имеет уникальную закладку. Вы можете получить закладку для текущей записи, `GetBookmark` `COleVariant` позвонив и сохранив значение объекту. Позже вы можете вернуться `SetBookmark` к этой записи, позвонив по сохраненному значению закладки.

> [!NOTE]
> Вызов [повторного изменения](#requery) DAO закладки.

Обратите внимание, что если вы не создаете набор записей UNICODE, `COleVariant` объект должен быть явно объявлен ANSI. Это может быть сделано с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `VT_BSTRT` `COleVariant` **,** *(lpszSrc* , *vtSrc* **)** форма конструктора с *vtSrc* набор (ANSI) или с помощью функции [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *(lpszSrc* **,** *vtSrc* **)** с *vtSrc* установить на .**(**

Для получения соответствующей информации, см.

## <a name="cdaorecordsetsetcachesize"></a><a name="setcachesize"></a>CDaoRecordset::SetCacheSize

Вызовите эту функцию участника, чтобы установить количество записей, которые будут кэшированы.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Параметры

*lРазмер*<br/>
Определяет количество записей. Типичное значение 100. Настройка 0 выключает кэширование. Настройка должна быть между 5 и 1200 записями. Кэш может использовать значительное количество памяти.

### <a name="remarks"></a>Remarks

Кэш — это пространство в локальной памяти, в мещавх данных, полученных с последнего времени с сервера, в случае, если данные будут запрошены снова во время работы приложения. Кэширование данных повышает производительность приложения, которое получает данные с удаленного сервера через объекты записей типа динасета. При запросе данных движок базы данных Microsoft Jet сначала проверяет кэш для запрашиваемых данных, а не изыскает его с сервера, что занимает больше времени. Данные, не полученные из источника данных ODBC, не сохраняются в кэше.

Любой источник данных ODBC, например прилагаемая таблица, может иметь локальный кэш. Чтобы создать кэш, откройте объект записи из удаленного источника данных, вызовите `SetCacheSize` функции и `SetCacheStart` функции участника, а затем вызовите функцию `FillCache` участника или шагчерез записи, используя одну из операций Move. Параметр *lSize* `SetCacheSize` функции участника может быть основан на количестве записей, с которые может работать ваше приложение одновременно. Например, если вы используете запись в качестве источника данных, которые будут `SetCacheSize` отображаться на экране, можно передать параметр *lSize* как 20 для отображения 20 записей одновременно.

Для получения соответствующей информации смотрите тему "Кэш-Изгой, КэшСтарт Свойства" в Справке DAO.

## <a name="cdaorecordsetsetcachestart"></a><a name="setcachestart"></a>CDaoRecordset::SetCacheStart

Позвоните в эту функцию участника, чтобы указать закладку первой записи в наборе записей, которая будет кэширована.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
[COleVariant,](../../mfc/reference/colevariant-class.md) который определяет закладку первой записи в рекорде, которая будет кэширована.

### <a name="remarks"></a>Remarks

Значение закладки любой записи можно использовать для `SetCacheStart` параметра *varBookmark* функции участника. Сделайте запись, которую вы хотите запустить кэш с текущей записью, установите закладку для этой `SetCacheStart` записи с помощью [SetBookmark](#setbookmark)и передайте значение закладки в качестве параметра для функции члена.

Движок базы данных Microsoft Jet запрашивает записи в диапазоне кэша от кэша и запрашивает записи за пределами диапазона кэша с сервера.

Записи, извлеченные из кэша, не отражают изменений, внесенных одновременно с исходными данными другими пользователями.

Чтобы заставить обновить все кэшированные данные, `SetCacheSize` передайте `SetCacheSize` параметр *lSize* как 0, позвоните снова с `FillCache` размером первоначально запрошенного кэша, а затем позвоните функции элемента.

Обратите внимание, что если вы не создаете набор записей UNICODE, `COleVariant` объект должен быть явно объявлен ANSI. Это может быть сделано с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `VT_BSTRT` `COleVariant` **,** *(lpszSrc* , *vtSrc* **)** форма конструктора с *vtSrc* набор (ANSI) или с помощью функции [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *(lpszSrc* **,** *vtSrc* **)** с *vtSrc* установить на .**(**

Для получения соответствующей информации смотрите тему CacheSize, Свойства Кэш-Старт" в справке DAO.

## <a name="cdaorecordsetsetcurrentindex"></a><a name="setcurrentindex"></a>CDaoRecordset::SetCurrentIndex

Вызовите эту функцию участника, чтобы установить индекс на наборе записей типа таблицы.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*lpszИндекс*<br/>
Указатель, содержащий название указателя, который будет установлен.

### <a name="remarks"></a>Remarks

Записи в базовых таблицах не хранятся в определенном порядке. Установка индекса изменяет порядок записей, возвращенных из базы данных, но не влияет на порядок хранения записей. Указанный индекс уже должен быть определен. Если вы попытаетесь использовать объект индекса, который не существует, или если индекс не установлен при вызове [Seek,](#seek)MFC бросает исключение.

Вы можете создать новый индекс для таблицы, позвонив [по телефону CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) и приложив новый индекс к сбору индексов базовой таблицы, позвонив [по cDaoTableDef::Append,](../../mfc/reference/cdaotabledef-class.md#append)а затем вновь открыв запись.

Записи, возвращенные из набора записей типа таблицы, могут быть заказаны только индексами, определенными для базовой таблицы. Для сортировки записей в каком-либо другом порядке можно открыть запись типа динасета или моментального снимка, используя положение S'L **ORDERBY,** хранящееся в [CDaoRecordset::m_strSort](#m_strsort).

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetsetfielddirty"></a><a name="setfielddirty"></a>CDaoRecordset::SetFieldDirty

Вызовите эту функцию участника, чтобы отметить полевой член данных, установленный в качестве измененного или неизмененного.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Содержит адрес члена полевых данных в наборе записей или NULL. Если NULL, все полевых данных в наборе записей помечены. (СЗ НУЛТ не то же самое, что Null в терминологии базы данных, что означает "не имеет значения.")

*bDirty*<br/>
ПРАВДА, если член данных поля должен быть помечен как "грязный" (изменен). В противном случае FALSE, если член данных полевого поля должен быть помечен как "чистый" (без изменений).

### <a name="remarks"></a>Remarks

Маркировка полей как неизменных гарантирует, что поле не обновляется.

Рамочные знаки изменили членов полевых данных, чтобы убедиться, что они будут записаны на запись об источнике данных механизмом обмена полями записей DAO (DFX). Изменение значения поля обычно автоматически устанавливает поле грязным, поэтому вам `SetFieldDirty` редко придется звонить себе, но иногда может потребоваться гарантировать, что столбцы будут явно обновлены или вставлены независимо от того, какое значение находится в составе члена данных поля. Механизм DFX также использует ПОДННУЛЛ. Для получения дополнительной информации, см [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойного буферизации не используется, то изменение значения поля автоматически не устанавливает поле как грязное. В этом случае необходимо будет четко установить поле как грязное. Флаг, содержащийся в [m_bCheckCacheForDirtyFields,](#m_bcheckcachefordirtyfields) контролирует эту автоматическую проверку поля.

> [!NOTE]
> Позвоните в эту функцию участника только после того, как вы позвонили [edit](#edit) или [AddNew](#addnew).

Использование NULL для первого аргумента функции `outputColumn` будет применять функцию `CDaoFieldExchange`для всех полей, а не **параполя** в . Например, вызов

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

установит только `outputColumn` поля NULL; **пара** поля будут затронуты.

Для работы над **парамом**необходимо предоставить фактический адрес отдельного **пара,** над ним вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Это означает, что вы не можете установить `outputColumn` все поля **параnull,** как вы можете с полями.

`SetFieldDirty`реализуется `DoFieldExchange`через .

## <a name="cdaorecordsetsetfieldnull"></a><a name="setfieldnull"></a>CDaoRecordset::SetFieldNull

Вызовите эту функцию участника, чтобы отметить полевой член данных, установленный как Null (конкретно не имеющий значения) или как не-Null.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Содержит адрес члена полевых данных в наборе записей или NULL. Если NULL, все полевых данных в наборе записей помечены. (СЗ НУЛТ не то же самое, что Null в терминологии базы данных, что означает "не имеет значения.")

*bNull*<br/>
Nonzero, если член данных полевого поля должен быть помечен как не имеющий значения (Null). В противном случае 0, если член данных поля должен быть помечен как не-Null.

### <a name="remarks"></a>Remarks

`SetFieldNull`используется для полей, `DoFieldExchange` связанных в механизме.

При добавлении новой записи в набор записей все участники полевых данных изначально устанавливаются на значение Null и помечаются как "грязные" (изменены). При извлечении записи из источника данных ее столбцы либо уже имеют значения, либо являются null. Если нецелесообразно делать поле Null, выбрасывается [CDaoException.](../../mfc/reference/cdaoexception-class.md)

Если вы используете механизм двойного буферизации, например, если вы специально хотите назначить поле `SetFieldNull` текущей записи как не имеющее значения, позвоните с *bNull,* чтобы TRUE пометить его как Null. Если поле ранее было помечено Null и теперь вы хотите придать ему значение, просто установите его новое значение. Вам не нужно снимать флаг `SetFieldNull`Null с . Чтобы определить, разрешено ли поле быть недействительным, позвоните [IsFieldNullable](#isfieldnullable).

Если вы не используете механизм двойного буферизации, то изменение значения поля автоматически не устанавливает поле как грязное и не-Null. Вы должны специально установить поля грязные и не-Null. Флаг, содержащийся в [m_bCheckCacheForDirtyFields,](#m_bcheckcachefordirtyfields) контролирует эту автоматическую проверку поля.

Механизм DFX использует ПОДННУЛЛ. Для получения дополнительной информации, см [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
> Позвоните в эту функцию участника только после того, как вы позвонили [edit](#edit) или [AddNew](#addnew).

Использование NULL для первого аргумента функции `outputColumn` будет применять сятвию только к полям, а не **к парам** полям в `CDaoFieldExchange`. Например, вызов

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

установит только `outputColumn` поля NULL; **пара** поля будут затронуты.

## <a name="cdaorecordsetsetfieldvalue"></a><a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue

Вызовите эту функцию участника, чтобы установить значение поля, либо по обычному положению, либо путем изменения значения строки.

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);

void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);

void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, содержащую имя поля.

*varValue*<br/>
Ссылка на объект [COleVariant,](../../mfc/reference/colevariant-class.md) содержащий значение содержимого поля.

*Nindex*<br/>
Цель, представляющая ординаторское положение поля в коллекции полей рекорда (на нулевой основе).

*lpszValue*<br/>
Указатель на строку, содержащую значение содержимого поля.

### <a name="remarks"></a>Remarks

Используйте `SetFieldValue` и [GetFieldValue](#getfieldvalue) динамически связывают поля во время выполнения, а не статически связывающие столбцы с помощью механизма [DoFieldExchange.](#dofieldexchange)

Обратите внимание, что если вы не создаете рекорд-сет `SetFieldValue` UNICODE, необходимо `COleVariant` либо использовать `COleVariant` форму, которая не содержит параметр, либо объект должен быть явно объявлен ANSI. Это может быть сделано с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `VT_BSTRT` `COleVariant` **,** *(lpszSrc* , *vtSrc* **)** форма конструктора с *vtSrc* набор (ANSI) или с помощью функции [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *(lpszSrc* **,** *vtSrc* **)** с *vtSrc* установить на .**(**

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetsetfieldvaluenull"></a><a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull

Вызовите эту функцию участника, чтобы установить поле к значению Null.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс поля в рекордном, для поиска по нулю основе индекса.

*lpszName*<br/>
Название поля в рекорде, для поиска по имени.

### <a name="remarks"></a>Remarks

СЗ НУЛЛ не то же самое, что Null, что, в терминологии базы данных, означает "не имеет значения".

Для получения соответствующей информации в справке DAO см.

## <a name="cdaorecordsetsetlockingmode"></a><a name="setlockingmode"></a>CDaoRecordset::SetLockingMode

Вызовите эту функцию участника, чтобы установить тип блокировки для набора записей.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Параметры

*bPessimistic*<br/>
Флаг, указывающий тип блокировки.

### <a name="remarks"></a>Remarks

Когда действует пессимистическая блокировка, страница 2K, содержащая запись, которая используется, `Edit` блокируется, как только вы звоните функции участника. Страница разблокирована, когда `Update` `Close` вы звоните функции или функции участника или любой из операций Move или Find.

При творке оптимистичной блокировки страница 2K, содержащая запись, `Update` блокируется только во время обновления записи с функцией участника.

Если страница заблокирована, ни один другой пользователь не может отсеить записи на той же странице. Если вы `SetLockingMode` звоните и передаете значение ненулевого значения и другой пользователь `Edit`уже заблокирован, при вызове вы бросаете исключение, когда вы звоните. Другие пользователи могут читать данные с заблокированных страниц.

Если вы `SetLockingMode` звоните с нулевым значением, а затем звоните, `Update` пока страница заблокирована другим пользователем, происходит исключение. Чтобы увидеть изменения, внесенные в вашу запись другим пользователем (и потерять ваши изменения), позвоните функции `SetBookmark` участника со значением закладки текущей записи.

При работе с источниками данных ODBC режим блокировки всегда оптимистичен.

## <a name="cdaorecordsetsetparamvalue"></a><a name="setparamvalue"></a>CDaoRecordset::SetParamValue

Вызовите эту функцию участника, чтобы установить значение параметра в наборе записей во время выполнения.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Численное положение параметра в коллекции параметров запроса.

*Var*<br/>
Значение для установки; увидеть замечания.

*lpszName*<br/>
Имя параметра, значение которого вы хотите установить.

### <a name="remarks"></a>Remarks

Параметр уже был установлен как часть строки с S'L. Вы можете получить доступ к параметру либо по имени, либо по его индексному положению в коллекции.

Укажите значение, установленное `COleVariant` как объект. Для получения информации об установлении желаемого [COleVariant](../../mfc/reference/colevariant-class.md)значения и вводе `COleVariant` объекта см. Обратите внимание, что если вы не создаете набор записей UNICODE, `COleVariant` объект должен быть явно объявлен ANSI. Это может быть сделано с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant) `VT_BSTRT` `VT_BSTRT` `COleVariant` **,** *(lpszSrc* , *vtSrc* **)** форма конструктора с *vtSrc* набор (ANSI) или с помощью функции [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *(lpszSrc* **,** *vtSrc* **)** с *vtSrc* установить на .**(**

## <a name="cdaorecordsetsetparamvaluenull"></a><a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull

Вызовите эту функцию участника, чтобы установить параметр к значению Null.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс поля в рекордном, для поиска по нулю основе индекса.

*lpszName*<br/>
Название поля в рекорде, для поиска по имени.

### <a name="remarks"></a>Remarks

СЗ НУЛЛ не то же самое, что Null, что, в терминологии базы данных, означает "не имеет значения".

## <a name="cdaorecordsetsetpercentposition"></a><a name="setpercentposition"></a>CDaoRecordset::SetPercentPosition

Вызовите эту функцию участника, чтобы установить значение, изменяя приблизительное местоположение текущей записи в объекте записи на основе процента записей в наборе записей.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Параметры

*fПозиция*<br/>
Число от 0 до 100.

### <a name="remarks"></a>Remarks

При работе с динасетом типа или моментального типа рекорда, сначала заполнить рекорд, `SetPercentPosition`перейдя к последней записи, прежде чем вы позвоните . Если вы `SetPercentPosition` звоните перед полной заполнением рекорда, количество движения относительно количества записей, к которым обращаются, как указано в значении [GetRecordCount.](#getrecordcount) Вы можете перейти к `MoveLast`последней записи, позвонив .

Как только `SetPercentPosition`вы звоните, запись в приблизительном положении, соответствующем этому значению, становится актуальной.

> [!NOTE]
> Вызов `SetPercentPosition` для перемещения текущей записи в определенной записи в рекордном наборе не рекомендуется. Вместо этого позвоните в функцию участника [SetBookmark.](#setbookmark)

Для получения соответствующей информации, см.

## <a name="cdaorecordsetupdate"></a><a name="update"></a>CDaoRecordset::Обновление

Вызов ими функции участника `AddNew` `Edit` после вызова к функции или функции участника.

```
virtual void Update();
```

### <a name="remarks"></a>Remarks

Этот вызов необходим для `AddNew` `Edit` завершения или операции.

`AddNew` И, `Edit` и подготовьте буфер редактирования, в котором добавленные или отредактированные данные размещаются для сохранения источника данных. `Update`сохраняет данные. Обновляются только те поля, которые отмечены или обнаружены как измененные.

Если источник данных поддерживает транзакции, можно сделать `Update` вызов (и его соответствующий `AddNew` или `Edit` колл) частью транзакции.

> [!CAUTION]
> Если вы `Update` звоните `AddNew` без `Edit` `Update` первого `CDaoException`вызова либо или , бросает . Если вы `AddNew` `Edit`звоните или, вы должны позвонить, `Update` прежде чем вы позвоните [MoveNext](#movenext) или закрыть либо рекорд-сет или подключение источника данных. В противном случае изменения теряются без уведомления.

Когда объект записи пессимистично заблокирован в многопользовательской среде, запись `Edit` остается заблокированной от времени, используемого до завершения обновления. Если запись оптимистически заблокирована, запись заблокирована и сравнивается с предварительно отредактированной записью непосредственно перед ее обновлением в базе данных. Если запись изменилась с `Edit`момента `Update` вызова, операция не удается, и MFC бросает исключение. Вы можете изменить режим `SetLockingMode`блокировки с .

> [!NOTE]
> Оптимистичная блокировка всегда используется на внешних форматах баз данных, таких как ODBC и устанавливаемый ISAM.

Для получения соответствующей информации в справке DAO(EditMode) смотрите темы :AddNew Method», «Метод отмены обновления», «Метод удаления», «Метод обновления» и «EditMode Property».

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase Класс](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CДао-КуириДеф](../../mfc/reference/cdaoquerydef-class.md)<br/>
