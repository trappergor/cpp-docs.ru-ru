---
title: Класс CDaoRecordset
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
ms.openlocfilehash: 96118645aa656e97fcb93a0fd223045208ab03a3
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424539"
---
# <a name="cdaorecordset-class"></a>Класс CDaoRecordset

Представляет набор записей, выбранных из источника данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CDaoRecordset:: CDaoRecordset](#cdaorecordset)|Формирует объект `CDaoRecordset`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CDaoRecordset:: AddNew](#addnew)|Подготовка к добавлению новой записи. Вызовите [Update](#update) , чтобы завершить добавление.|
|[CDaoRecordset:: Канаппенд](#canappend)|Возвращает ненулевое значение, если новые записи можно добавить в набор записей с помощью функции члена [AddNew](#addnew) .|
|[CDaoRecordset:: Канбукмарк](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|
|[CDaoRecordset:: CancelUpdate](#cancelupdate)|Отменяет все ожидающие обновления из-за операции [Edit](#edit) или [AddNew](#addnew) .|
|[CDaoRecordset:: Канрестарт](#canrestart)|Возвращает ненулевое значение, если можно вызвать метод [Requery](#requery) для повторного выполнения запроса набора записей.|
|[CDaoRecordset:: Канскролл](#canscroll)|Возвращает ненулевое значение, если можно выполнить прокрутку записей.|
|[CDaoRecordset:: Кантрансакт](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|
|[CDaoRecordset:: Канупдате](#canupdate)|Возвращает ненулевое значение, если набор записей может быть обновлен (можно добавлять, обновлять или удалять записи).|
|[CDaoRecordset:: Close](#close)|Закрывает набор записей.|
|[CDaoRecordset::D удалить](#delete)|Удаляет текущую запись из набора записей. После удаления необходимо явно прокрутить на другую запись.|
|[CDaoRecordset::D Офиелдексчанже](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных поля набора записей и соответствующей записью в источнике данных. Реализует обмен полями записей DAO (DFX).|
|[CDaoRecordset:: Edit](#edit)|Подготавливает изменения к текущей записи. Вызовите `Update`, чтобы завершить изменение.|
|[CDaoRecordset:: Филлкаче](#fillcache)|Заполняет все или часть локального кэша объектом набора записей, который содержит данные из источника данных ODBC.|
|[CDaoRecordset:: Find](#find)|Находит первое, следующее, предыдущее или Последнее расположение определенной строки в наборе записей динамического набора данных, удовлетворяющего заданным критериям, и делает запись текущей записью.|
|[CDaoRecordset:: FindFirst](#findfirst)|Находит первую запись в динамическом наборе записей типа или моментального снимка, удовлетворяющем заданным критериям, и делает запись текущей записью.|
|[CDaoRecordset:: FindLast](#findlast)|Находит последнюю запись в динамическом наборе записей типа или снимке, удовлетворяющем заданным критериям, и делает запись текущей.|
|[CDaoRecordset:: FindNext](#findnext)|Находит следующую запись в динамическом наборе записей типа или снимке, удовлетворяющем заданным критериям, и делает запись текущей.|
|[CDaoRecordset:: Финдпрев](#findprev)|Находит предыдущую запись в динамическом типе или наборе записей моментального снимка, который удовлетворяет заданным критериям, и делает запись текущей записью.|
|[CDaoRecordset:: Жетабсолутепоситион](#getabsoluteposition)|Возвращает номер записи текущей записи объекта набора записей.|
|[CDaoRecordset:: onbookmark](#getbookmark)|Возвращает значение, представляющее закладку в записи.|
|[CDaoRecordset:: Жеткачесизе](#getcachesize)|Возвращает значение, указывающее количество записей в наборе записей динамического типа, содержащего данные, которые должны быть локально кэшированы из источника данных ODBC.|
|[CDaoRecordset:: Жеткачестарт](#getcachestart)|Возвращает значение, указывающее закладку первой записи в наборе записей для кэширования.|
|[CDaoRecordset:: Жеткуррентиндекс](#getcurrentindex)|Возвращает `CString`, содержащий имя индекса, который последним использовался в индексированном табличном табличном типе `CDaoRecordset`.|
|[CDaoRecordset:: Жетдатекреатед](#getdatecreated)|Возвращает дату и время создания базовой таблицы, лежащей в основе объекта `CDaoRecordset`|
|[CDaoRecordset:: Жетдателаступдатед](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенного в проект базовой таблицы, на основе объекта `CDaoRecordset`.|
|[CDaoRecordset:: Жетдефаултдбнаме](#getdefaultdbname)|Возвращает имя источника данных по умолчанию.|
|[CDaoRecordset:: GetDefaultSQL](#getdefaultsql)|Вызывается для получения строки SQL по умолчанию для выполнения.|
|[CDaoRecordset:: Жетедитмоде](#geteditmode)|Возвращает значение, указывающее состояние редактирования для текущей записи.|
|[CDaoRecordset:: Жетфиелдкаунт](#getfieldcount)|Возвращает значение, представляющее количество полей в наборе записей.|
|[CDaoRecordset:: Жетфиелдинфо](#getfieldinfo)|Возвращает определенные виды информации о полях в наборе записей.|
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|
|[CDaoRecordset:: Жетиндекскаунт](#getindexcount)|Возвращает количество индексов в таблице, лежащей в основе набора записей.|
|[CDaoRecordset:: Жетиндексинфо](#getindexinfo)|Возвращает различные типы сведений о индексе.|
|[CDaoRecordset:: Жетластмодифиедбукмарк](#getlastmodifiedbookmark)|Используется для определения самой последней добавленной или обновленной записи.|
|[CDaoRecordset:: Жетлоккингмоде](#getlockingmode)|Возвращает значение, указывающее тип блокировки, действующей во время редактирования.|
|[CDaoRecordset:: Name](#getname)|Возвращает `CString`, содержащий имя набора записей.|
|[CDaoRecordset:: Жетпарамвалуе](#getparamvalue)|Извлекает текущее значение указанного параметра, хранящегося в базовом объекте Даопараметер.|
|[CDaoRecordset:: Жетперцентпоситион](#getpercentposition)|Возвращает расположение текущей записи в процентах от общего числа записей.|
|[CDaoRecordset:: Жетрекордкаунт](#getrecordcount)|Возвращает число записей, к которым осуществлялось обращение в объекте Recordset.|
|[CDaoRecordset:: Жетскл](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|
|[CDaoRecordset:: GetType](#gettype)|Вызывается для определения типа набора записей: тип таблицы, динамический набор или тип моментального снимка.|
|[CDaoRecordset:: Жетвалидатионруле](#getvalidationrule)|Возвращает `CString`, содержащий значение, которое проверяет данные по мере их введения в поле.|
|[CDaoRecordset:: Жетвалидатионтекст](#getvalidationtext)|Извлекает текст, который отображается, если правило проверки не удовлетворено.|
|[CDaoRecordset:: Исбоф](#isbof)|Возвращает ненулевое значение, если набор записей был помещен перед первой записью. Нет текущей записи.|
|[CDaoRecordset:: isDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей расположен на удаленной записи.|
|[CDaoRecordset:: Исеоф](#iseof)|Возвращает ненулевое значение, если набор записей был помещен после последней записи. Нет текущей записи.|
|[CDaoRecordset:: Исфиелддирти](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи было изменено.|
|[CDaoRecordset:: Исфиелднулл](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение null (не имеет значения).|
|[CDaoRecordset:: Исфиелднуллабле](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи может быть установлено в NULL (без значения).|
|[CDaoRecordset:: OnOpen](#isopen)|Возвращает ненулевое значение, если метод [Open](#open) был вызван ранее.|
|[CDaoRecordset:: Move](#move)|Размещает набор записей по заданному числу записей из текущей записи в любом направлении.|
|[CDaoRecordset:: MoveFirst](#movefirst)|Позиционирует текущую запись в первой записи в наборе записей.|
|[CDaoRecordset:: MoveLast](#movelast)|Позиционирует текущую запись по последней записи в наборе записей.|
|[CDaoRecordset:: MoveNext](#movenext)|Позиционирует текущую запись на следующую запись в наборе записей.|
|[CDaoRecordset:: Мовепрев](#moveprev)|Позиционирует текущую запись о предыдущей записи в наборе записей.|
|[CDaoRecordset:: Open](#open)|Создает новый набор записей из таблицы, динамического набора или моментального снимка.|
|[CDaoRecordset:: Requery](#requery)|Повторно выполняет запрос набора записей, чтобы обновить выбранные записи.|
|[CDaoRecordset:: Seek](#seek)|Находит запись в индексированном табличном типе объекта Recordset, удовлетворяющего заданным условиям для текущего индекса, и делает запись текущей записью.|
|[CDaoRecordset:: Сетабсолутепоситион](#setabsoluteposition)|Задает номер записи текущей записи объекта набора записей.|
|[CDaoRecordset:: Сетбукмарк](#setbookmark)|Размещает набор записей для записи, содержащей указанную закладку.|
|[CDaoRecordset:: Сеткачесизе](#setcachesize)|Задает значение, указывающее количество записей в наборе записей динамического типа, содержащего данные, которые должны быть локально кэшированы из источника данных ODBC.|
|[CDaoRecordset:: Сеткачестарт](#setcachestart)|Задает значение, указывающее закладку первой записи в наборе записей для кэширования.|
|[CDaoRecordset:: Сеткуррентиндекс](#setcurrentindex)|Вызывается для задания индекса в наборе записей типа таблицы.|
|[CDaoRecordset:: Сетфиелддирти](#setfielddirty)|Помечает указанное поле в текущей записи как измененное.|
|[CDaoRecordset:: Сетфиелднулл](#setfieldnull)|Устанавливает значение указанного поля в текущей записи в значение null (без значения).|
|[CDaoRecordset:: Сетфиелдвалуе](#setfieldvalue)|Задает значение поля в наборе записей.|
|[CDaoRecordset:: Сетфиелдвалуенулл](#setfieldvaluenull)|Устанавливает значение поля в наборе записей равным null. (не имеет значения).|
|[CDaoRecordset:: Сетлоккингмоде](#setlockingmode)|Задает значение, указывающее тип блокировки, которая будет применяться во время редактирования.|
|[CDaoRecordset:: Сетпарамвалуе](#setparamvalue)|Задает текущее значение указанного параметра, хранящегося в базовом объекте Даопараметер|
|[CDaoRecordset:: Сетпарамвалуенулл](#setparamvaluenull)|Устанавливает текущее значение указанного параметра в значение null (без значения).|
|[CDaoRecordset:: Сетперцентпоситион](#setpercentposition)|Устанавливает позицию текущей записи в расположение, соответствующее проценту от общего числа записей в наборе записей.|
|[CDaoRecordset:: Update](#update)|Завершает операцию `AddNew` или `Edit`, сохраняя новые или измененные данные в источнике данных.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[CDaoRecordset:: m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Содержит флаг, указывающий, будут ли поля автоматически помечены как измененные.|
|[CDaoRecordset:: m_nFields](#m_nfields)|Содержит количество элементов данных полей в классе набора записей и число столбцов, выбранных набором записей из источника данных.|
|[CDaoRecordset:: m_nParams](#m_nparams)|Содержит число элементов данных параметров в классе набора записей — количество параметров, передаваемых с помощью запроса набора записей.|
|[CDaoRecordset:: m_pDAORecordset](#m_pdaorecordset)|Указатель на интерфейс DAO, лежащий в основе объекта Recordset.|
|[CDaoRecordset:: m_pDatabase](#m_pdatabase)|База данных источника для этого результирующего набора. Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .|
|[CDaoRecordset:: m_strFilter](#m_strfilter)|Содержит строку, используемую для создания инструкции SQL **WHERE** .|
|[CDaoRecordset:: m_strSort](#m_strsort)|Содержит строку, используемую для создания инструкции SQL **ORDER BY** .|

## <a name="remarks"></a>Remarks

`CDaoRecordset` объекты, называемые "наборами записей", доступны в следующих трех формах:

- Наборы записей табличного типа представляют базовую таблицу, которую можно использовать для проверки, добавления, изменения или удаления записей из одной таблицы базы данных.

- Наборы записей типа динамического набора являются результатом запроса, который может иметь обновляемые записи. Эти наборы записей представляют собой набор записей, которые можно использовать для проверки, добавления, изменения или удаления записей из базовой таблицы или таблиц базы данных. Наборы записей динамического набора могут содержать поля из одной или нескольких таблиц в базе данных.

- Наборы записей типа snapshot — это статические копии набора записей, которые можно использовать для поиска данных или создания отчетов. Эти наборы записей могут содержать поля из одной или нескольких таблиц в базе данных, но не могут быть обновлены.

Каждая форма набора записей представляет набор записей, фиксированных во время открытия набора записей. При переходе к записи в наборе записей типа таблицы или динамическом наборе записей он отражает изменения, внесенные в запись после открытия набора записей другими пользователями или другими наборами записей в приложении. (Набор записей типа SNAPSHOT не может быть обновлен.) Можно использовать `CDaoRecordset` напрямую или создать класс набора записей, зависящий от приложения, от `CDaoRecordset`. Можно выполнить следующее.

- Прокрутите записи.

- Задайте индекс и быстро ищите записи с помощью [Seek](#seek) (только наборы записей типа "Таблица-Тип").

- Поиск записей на основе сравнения строк: "<", "\<=", "=", "> =" или ">" (наборы записей динамического набора и типа моментальных снимков).

- Обновите записи и укажите режим блокировки (за исключением наборов записей типа snapshot).

- Отфильтруйте набор записей, чтобы ограничить выбор выбираемых записей из доступных в источнике данных.

- Сортировка набора записей.

- Параметризация набора записей для настройки его выбора со сведениями, неизвестными до времени выполнения.

Класс `CDaoRecordset` предоставляет интерфейс, аналогичный классу `CRecordset`. Основное отличие заключается в том, что класс `CDaoRecordset` обращается к данным через объект доступа к данным (DAO), основанный на OLE. Класс `CRecordset` обращается к СУБД через ODBC и драйвер ODBC для этой СУБД.

> [!NOTE]
> Классы базы данных DAO отличаются от классов баз данных MFC, основанных на открытом подключении к базам данных (ODBC). Все имена классов баз данных DAO имеют префикс "Кдао". Вы по-прежнему можете обращаться к источникам данных ODBC с помощью классов DAO. классы DAO обычно предлагают превосходные возможности, поскольку они характерны для ядра СУБД Microsoft Jet.

Можно либо использовать `CDaoRecordset` напрямую, либо создать производный класс от `CDaoRecordset`. Чтобы использовать класс Recordset в любом случае, откройте базу данных и создайте объект набора записей, передав конструктору указатель на объект `CDaoDatabase`. Можно также создать объект `CDaoRecordset` и позволить MFC создавать временный объект `CDaoDatabase`. Затем вызовите функцию [открытого](#open) члена набора записей, указав, является ли объект набором записей типа Table, динамическим набором или набором записей типа snapshot. При вызове `Open` выбираются данные из базы данных и извлекается первая запись.

Используйте функции-члены и элементы данных объекта для прокрутки записей и работы с ними. Доступные операции зависят от того, является ли объект набором записей типа Table, динамическим набором данных или набором записей моментального снимка и является ли он доступным для обновления или только для чтения. это зависит от возможностей базы данных или открытого подключения к базе данных (ODBC). Источник данных. Чтобы обновить записи, которые могли быть изменены или добавлены с момента вызова `Open`, вызовите [функцию члена обновления](#requery) для объекта. Вызовите функцию члена `Close` объекта и удалите объект после завершения работы с ним.

`CDaoRecordset` использует обмен полями записей DAO (DFX) для поддержки чтения и обновления полей записей с помощью строго типизированных C++ членов класса `CDaoRecordset` или производного от `CDaoRecordset`классов. Кроме того, можно реализовать динамическую привязку столбцов в базе данных без использования механизма DFX с использованием [GetFieldValue](#getfieldvalue) и [сетфиелдвалуе](#setfieldvalue).

Связанные сведения см. в разделе «объект набора записей» справки DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

##  <a name="addnew"></a>CDaoRecordset:: AddNew

Вызовите эту функцию-член, чтобы добавить новую запись в набор записей типа table или динамического набора.

```
virtual void AddNew();
```

### <a name="remarks"></a>Remarks

Поля записи изначально имеют значение null. (В терминологии базы данных значение NULL означает, что значение не имеет значения и не совпадает со значением C++NULL в.) Чтобы завершить операцию, необходимо вызвать функцию [обновления](#update) члена. `Update` сохраняет изменения в источнике данных.

> [!CAUTION]
>  Если изменить запись, а затем перейти к другой записи без вызова `Update`, изменения будут потеряны без предупреждения.

Если добавить запись в набор записей динамического набора с помощью вызова метода [AddNew](#addnew), запись будет видна в наборе записей и включена в базовую таблицу, где она становится видимой для любых новых объектов `CDaoRecordset`.

Расположение новой записи зависит от типа набора записей.

- В наборе записей динамического типа, в который вставляется новая запись, не гарантируется. Это поведение изменено с помощью Microsoft Jet 3,0 в целях повышения производительности и параллелизма. Если ваша цель — сделать вновь добавленную запись текущей записи, получите закладку последней измененной записи и перейдите к этой закладке:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- В наборе записей табличного типа, для которого был указан индекс, записи возвращаются в правильном месте в порядке сортировки. Если индекс не указан, в конце набора записей возвращаются новые записи.

Запись, которая была текущей до использования `AddNew`, остается актуальной. Если вы хотите сделать новую запись текущей и набор записей поддерживает закладки, вызовите [сетбукмарк](#setbookmark) для закладки, определяемой параметром свойства LastModified базового объекта Recordset DAO. Это полезно для определения значения полей счетчика (автоприращения) в добавленной записи. Дополнительные сведения см. в разделе [жетластмодифиедбукмарк](#getlastmodifiedbookmark).

Если база данных поддерживает транзакции, можно сделать `AddNew` вызовом части транзакции. Дополнительные сведения о транзакциях см. в разделе Class [кдаоворкспаце](../../mfc/reference/cdaoworkspace-class.md). Обратите внимание, что перед вызовом `AddNew`необходимо вызвать метод [кдаоворкспаце:: примеры BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) .

Не допускается вызов `AddNew` для набора записей, для которого не была вызвана функция [Open](#open) Member. При вызове `AddNew` для набора записей, который не может быть добавлен, создается `CDaoException`. Чтобы определить, можно ли обновить набор записей путем вызова [канаппенд](#canappend).

Платформа помечает измененные элементы данных поля, чтобы убедиться, что они будут записаны в запись в источнике данных с помощью механизма обмена полями записей DAO (DFX). Изменение значения поля обычно устанавливает поле как "грязное" автоматически, поэтому вам редко приходится вызывать [сетфиелддирти](#setfielddirty) самостоятельно, но иногда требуется обеспечить явное обновление или вставку столбцов независимо от значения в элементе данных поля. Механизм DFX также использует **псевдо NULL**. Дополнительные сведения см. в разделе [кдаофиелдексчанже:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойной буферизации не используется, то изменение значения поля не приводит к автоматическому заданию поля как «грязное». В этом случае необходимо явно задать поле «грязный». Флаг, содержащийся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) , управляет этой автоматической проверкой полей.

> [!NOTE]
> Если записи двойно буферизованы (то есть включена автоматическая проверка полей), вызов `CancelUpdate` восстановит переменные-члены до вызова `AddNew` или `Edit`.

Дополнительные сведения см. в разделах "метод AddNew", "метод CancelUpdate", "свойство LastModified" и "свойство EditMode" справки DAO.

##  <a name="canappend"></a>CDaoRecordset:: Канаппенд

Вызовите эту функцию члена, чтобы определить, позволяет ли ранее открытый набор записей добавлять новые записи путем вызова функции члена [AddNew](#addnew) .

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей допускает добавление новых записей; в противном случае — 0. `CanAppend` возвращает 0, если набор записей открыт только для чтения.

### <a name="remarks"></a>Remarks

Связанные сведения см. в разделе "метод Append" справки DAO.

##  <a name="canbookmark"></a>CDaoRecordset:: Канбукмарк

Вызовите эту функцию члена, чтобы определить, позволяет ли ранее открытый набор записей отдельно отмечать записи с помощью закладок.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей поддерживает закладки; в противном случае — 0.

### <a name="remarks"></a>Remarks

При использовании наборов записей, полностью основанных на таблицах ядра СУБД Microsoft Jet, можно использовать закладки, за исключением наборов записей типа snapshot, помеченных как однопроходные наборы записей с прокруткой. Другие продукты базы данных (внешние источники данных ODBC) могут не поддерживать закладки.

Дополнительные сведения см. в разделе "свойство с закладками" справки DAO.

##  <a name="cancelupdate"></a>CDaoRecordset:: CancelUpdate

Функция-член `CancelUpdate` отменяет все ожидающие обновления в результате операции [Edit](#edit) или [AddNew](#addnew) .

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Remarks

Например, если приложение вызывает функцию члена `Edit` или `AddNew` и не вызвала [Update](#update), `CancelUpdate` отменяет все изменения, внесенные после вызова `Edit` или `AddNew`.

> [!NOTE]
>  Если записи двойно буферизованы (то есть включена автоматическая проверка полей), вызов `CancelUpdate` восстановит переменные-члены до вызова `AddNew` или `Edit`.

Если `Edit` или `AddNew` ожидающие выполнения операции, `CancelUpdate` вынуждает MFC вызывать исключение. Вызовите функцию-член [жетедитмоде](#geteditmode) , чтобы определить, существует ли отложенная операция, которую можно отменить.

Связанные сведения см. в разделе «метод CancelUpdate» справки DAO.

##  <a name="canrestart"></a>CDaoRecordset:: Канрестарт

Вызовите эту функцию-член, чтобы определить, позволяет ли набор записей перезапускать свой запрос (чтобы обновить записи), вызвав функцию-член `Requery`.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если можно вызвать `Requery` для повторного выполнения запроса набора записей; в противном случае — 0.

### <a name="remarks"></a>Remarks

Наборы записей табличного типа не поддерживают `Requery`.

Если `Requery` не поддерживается, вызовите [Close](#close) , а затем [Open](#open) , чтобы обновить данные. Можно вызвать `Requery`, чтобы обновить запрос к базовому параметру объекта набора записей после изменения значений параметров.

Связанные сведения см. в разделе "перезапускаемое свойство" справки DAO.

##  <a name="canscroll"></a>CDaoRecordset:: Канскролл

Вызовите эту функцию члена, чтобы определить, допускает ли набор записей прокрутку.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если можно выполнить прокрутку записей, в противном случае — 0.

### <a name="remarks"></a>Remarks

При вызове метода [Open](#open) с `dbForwardOnly`набор записей может прокручиваться вперед.

Дополнительные сведения см. в подразделе «размещение указателя текущей записи с помощью DAO» справки DAO.

##  <a name="cantransact"></a>CDaoRecordset:: Кантрансакт

Вызовите эту функцию члена, чтобы определить, допускает ли набор записей транзакции.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если базовый источник данных поддерживает транзакции, в противном случае — 0.

### <a name="remarks"></a>Remarks

Связанные сведения см. в разделе "свойства транзакций" справки DAO.

##  <a name="canupdate"></a>CDaoRecordset:: Канупдате

Вызовите эту функцию члена, чтобы определить, можно ли обновить набор записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей может обновляться (добавлять, обновлять и удалять записи); в противном случае — 0.

### <a name="remarks"></a>Remarks

Набор записей может быть доступен только для чтения, если базовый источник данных доступен только для чтения или если вы указали `dbReadOnly` для *ноптионс* при вызове [Open](#open) для набора записей.

Дополнительные сведения см. в разделах "метод AddNew", "изменить метод", "метод удаления", "метод обновления" и "обновляемое свойство" справки DAO.

##  <a name="cdaorecordset"></a>CDaoRecordset:: CDaoRecordset

Формирует объект `CDaoRecordset`.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*пдатабасе*<br/>
Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) или значение null. Если не равно NULL и функция члена `Open` объекта `CDaoDatabase` не была вызвана для подключения к источнику данных, набор записей пытается открыть его для вас во время собственного [открытого](#open) вызова. При передаче значения NULL объект `CDaoDatabase` создается и подключается, используя сведения об источнике данных, которые вы указали, если класс набора записей был производным от `CDaoRecordset`.

### <a name="remarks"></a>Remarks

Можно либо использовать `CDaoRecordset` напрямую, либо получить класс, зависящий от приложения, от `CDaoRecordset`. ClassWizard можно использовать для получения классов набора записей.

> [!NOTE]
>  Если вы наследуете класс `CDaoRecordset`, производный класс должен предоставить собственный конструктор. В конструкторе производного класса вызовите конструктор `CDaoRecordset::CDaoRecordset`, передав ему соответствующие параметры.

Передайте значение NULL конструктору набора записей, чтобы объект `CDaoDatabase` был автоматически создан и подключен. Это полезный ярлык, который не требует создания и подключения объекта `CDaoDatabase` перед созданием набора записей. Если объект `CDaoDatabase` не открыт, будет также создан объект [кдаоворкспаце](../../mfc/reference/cdaoworkspace-class.md) , использующий рабочую область по умолчанию. Дополнительные сведения см. в разделе [CDaoDatabase:: CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

##  <a name="close"></a>CDaoRecordset:: Close

При закрытии объекта `CDaoRecordset` он удаляется из коллекции открытых наборов записей в связанной базе данных.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Поскольку `Close` не уничтожает объект `CDaoRecordset`, можно повторно использовать объект, вызвав `Open` в том же источнике данных или другом источнике данных.

Все отложенные инструкции [AddNew](#addnew) и [Edit](#edit) отменяются, а все ожидающие транзакции откатываются. Если вы хотите сохранить ожидающие добавления или изменения, вызовите [Обновление](#update) перед вызовом `Close` для каждого набора записей.

После вызова `Close`можно вызвать метод `Open`. Это позволяет повторно использовать объект Recordset. Лучшим вариантом является вызов метода [Requery](#requery), если это возможно.

Дополнительные сведения см. в разделе «метод закрытия» справки DAO.

##  <a name="delete"></a>CDaoRecordset::D удалить

Вызовите эту функцию-член, чтобы удалить текущую запись в открытом динамическом типе или объекте набора записей типа Table.

```
virtual void Delete();
```

### <a name="remarks"></a>Remarks

После успешного удаления элементы данных поля набора записей устанавливаются в значение null, и для перемещения удаленной записи необходимо явно вызвать одну из функций элементов навигации по набору записей ( [Перемещение](#move), [Поиск](#seek), [сетбукмарк](#setbookmark)и т. д.). При удалении записей из набора записей перед вызовом `Delete`должна существовать текущая запись в наборе записей. в противном случае MFC создает исключение.

`Delete` удаляет текущую запись и делает ее недоступной. Хотя вы не можете изменить или использовать удаленную запись, она останется текущей. Однако после перехода на другую запись ее нельзя будет сделать текущей.

> [!CAUTION]
>  Набор записей должен быть обновляемым, и при вызове `Delete`в наборе записей должна быть действительная запись. Например, если удалить запись, но не прокручивать до новой записи перед вызовом `Delete`, `Delete` выдаст исключение [кдаоексцептион](../../mfc/reference/cdaoexception-class.md).

Можно отменить удаление записи, если используются транзакции, и вызвать функцию-член [кдаоворкспаце:: ROLLBACK](../../mfc/reference/cdaoworkspace-class.md#rollback) . Если базовая таблица является первичной таблицей в связи Cascade DELETE, удаление текущей записи может также удалить одну или несколько записей во внешней таблице. Дополнительные сведения см. в описании каскадного удаления в справке DAO.

В отличие от `AddNew` и `Edit`, за вызовом `Delete` не следует вызов `Update`.

Дополнительные сведения см. в разделах "метод AddNew", "изменить метод", "метод удаления", "метод обновления" и "обновляемое свойство" справки DAO.

##  <a name="dofieldexchange"></a>CDaoRecordset::D Офиелдексчанже

Платформа вызывает эту функцию члена, чтобы автоматически обмениваться данными между элементами данных поля объекта Recordset и соответствующими столбцами текущей записи в источнике данных.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Сохраняется*<br/>
Содержит указатель на объект `CDaoFieldExchange`. Платформа уже настроит этот объект, чтобы указать контекст для операции обмена полями.

### <a name="remarks"></a>Remarks

Он также привязывает члены данных параметров, если таковые имеются, к заполнителям параметров в строке инструкции SQL для выбора набора записей. Обмен данными полей, называемый обмен полями записей DAO (DFX), работает в обоих направлениях: от элементов данных поля объекта набора записей к полям записи в источнике данных и от записи в источнике данных к объекту набора записей. При динамическом связывании столбцов не требуется реализовывать `DoFieldExchange`.

Единственное действие, которое необходимо выполнить для реализации `DoFieldExchange` для производного класса Recordset, — создать класс с ClassWizard и указать имена и типы данных для элементов данных поля. Вы также можете добавить код в запись ClassWizard для указания элементов данных параметров. Если все поля должны быть привязаны динамически, эта функция будет неактивна, если не указать элементы данных параметров.

При объявлении производного класса набора записей с помощью ClassWizard мастер записывает переопределение `DoFieldExchange`, которое напоминает следующий пример:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>CDaoRecordset:: Edit

Вызовите эту функцию члена, чтобы разрешить изменения в текущей записи.

```
virtual void Edit();
```

### <a name="remarks"></a>Remarks

После вызова функции члена `Edit` изменения, внесенные в поля текущей записи, копируются в буфер копирования. После внесения нужных изменений в запись вызовите `Update`, чтобы сохранить изменения. `Edit` сохраняет значения элементов данных набора записей. При вызове `Edit`, внесении изменений, а затем повторном вызове `Edit` значения записей восстанавливаются до первого вызова `Edit`.

> [!CAUTION]
>  Если изменить запись и затем выполнить любую операцию, которая перемещается в другую запись без предварительного вызова `Update`, изменения будут потеряны без предупреждения. Кроме того, если закрыть набор записей или родительскую базу данных, измененная запись будет удалена без предупреждения.

В некоторых случаях может потребоваться обновить столбец, сделав его нулевым (не содержащим данные). Для этого вызовите `SetFieldNull` с параметром TRUE, чтобы пометить поле как null; Это также приводит к обновлению столбца. Если необходимо, чтобы поле было записано в источник данных, даже если его значение не изменилось, вызовите `SetFieldDirty` с параметром TRUE. Это работает, даже если поле имеет значение null.

Платформа помечает измененные элементы данных поля, чтобы убедиться, что они будут записаны в запись в источнике данных с помощью механизма обмена полями записей DAO (DFX). Изменение значения поля обычно устанавливает поле как "грязное" автоматически, поэтому вам редко приходится вызывать [сетфиелддирти](#setfielddirty) самостоятельно, но иногда требуется обеспечить явное обновление или вставку столбцов независимо от значения в элементе данных поля. Механизм DFX также использует **псевдо NULL**. Дополнительные сведения см. в разделе [кдаофиелдексчанже:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойной буферизации не используется, то изменение значения поля не приводит к автоматическому заданию поля как «грязное». В этом случае необходимо явно задать поле «грязный». Флаг, содержащийся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) , управляет этой автоматической проверкой полей.

Если объект Recordset пессимистикалли заблокирован в многопользовательской среде, запись остается заблокированной с момента времени, `Edit` используется до завершения обновления. Если набор записей вызывает заблокирован, запись блокируется и сравнивается с предварительно измененной записью непосредственно перед ее обновлением в базе данных. Если запись изменилась с момента вызова `Edit`, операция `Update` завершается сбоем и MFC создает исключение. Режим блокировки можно изменить с помощью `SetLockingMode`.

> [!NOTE]
>  Оптимистическая блокировка всегда используется во внешних форматах базы данных, таких как ODBC и installed ISAM.

Текущая запись остается текущей после вызова `Edit`. Чтобы вызвать `Edit`, должна существовать текущая запись. Если нет текущей записи или если набор записей не ссылается на объект набора записей открытого типа Table-Type или динамического типа, возникает исключение. Вызов `Edit` вызывает исключение `CDaoException` при следующих условиях:

- Нет текущей записи.

- База данных или набор записей доступны только для чтения.

- Поля в записи не обновляются.

- База данных или набор записей были открыты для монопольного использования другим пользователем.

- Другой пользователь заблокировал страницу, содержащую вашу запись.

Если источник данных поддерживает транзакции, можно сделать `Edit` вызовом части транзакции. Обратите внимание, что следует вызвать метод `CDaoWorkspace::BeginTrans` перед вызовом `Edit` и после открытия набора записей. Также обратите внимание, что вызов `CDaoWorkspace::CommitTrans` не является заменой вызова `Update` для завершения операции `Edit`. Дополнительные сведения о транзакциях см. в разделе класс `CDaoWorkspace`.

Дополнительные сведения см. в разделах "метод AddNew", "изменить метод", "метод удаления", "метод обновления" и "обновляемое свойство" справки DAO.

##  <a name="fillcache"></a>CDaoRecordset:: Филлкаче

Вызовите эту функцию-член для кэширования указанного числа записей из набора записей.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Параметры

*псизе*<br/>
Указывает количество строк для заполнения в кэше. Если опустить этот параметр, значение определяется параметром свойства CacheSize базового объекта DAO.

*пбукмарк*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) , задающий закладку. Кэш заполняется начиная с записи, указанной в этой закладке. Если этот параметр не задан, кэш заполняется начиная с записи, указанной свойством Качестарт базового объекта DAO.

### <a name="remarks"></a>Remarks

Кэширование повышает производительность приложения, которое получает или извлекает данные с удаленного сервера. Кэш-память — это место в локальной памяти, в котором хранятся данные, наиболее часто извлекаемые с сервера с учетом предположения о том, что данные, скорее всего, будут запрошены во время работы приложения. При запросе данных ядро базы данных Microsoft Jet сначала проверяет кэш на наличие данных, а не извлекает его с сервера, что занимает больше времени. Использование кэширования данных в источниках данных, отличных от ODBC, не оказывает влияния, так как данные не сохраняются в кэше.

Вместо того чтобы ждать заполнения кэша записями при их выборке, можно в любое время заполнить кэш, вызвав функцию члена `FillCache`. Это более быстрый способ заполнения кэша, так как `FillCache` одновременно извлекает несколько записей, а не один раз. Например, при отображении каждой записи в каждом экране можно настроить вызов приложения `FillCache` для выборки следующего экрана записей.

Любая база данных ODBC, доступная с объектами набора записей, может иметь локальный кэш. Чтобы создать кэш, откройте объект набора записей из удаленного источника данных, а затем вызовите функции-члены `SetCacheSize` и `SetCacheStart` набора записей. Если *лсизе* и *лбукмарк* создают диапазон, который частично или полностью выходит за пределы диапазона, заданного `SetCacheSize` и `SetCacheStart`, часть набора записей за пределами этого диапазона игнорируется и не загружается в кэш. Если `FillCache` запрашивает больше записей, чем остается в удаленном источнике данных, выводятся только оставшиеся записи, и исключение не создается.

Записи, полученные из кэша, не отображают изменения, внесенные в исходные данные другими пользователями одновременно.

`FillCache` извлекает только записи, которые еще не были кэшированы. Чтобы принудительно обновить все кэшированные данные, вызовите функцию члена `SetCacheSize` с параметром *лсизе* , равным 0, вызовите `SetCacheSize` еще раз с параметром *лсизе* , равным первоначально запрошенному размеру кэша, а затем вызовите `FillCache`.

Связанные сведения см. в разделе «метод Филлкаче» справки DAO.

##  <a name="find"></a>CDaoRecordset:: Find

Вызовите эту функцию-член, чтобы нахождение конкретной строки в наборе записей динамического набора или типа моментального снимка с помощью оператора сравнения.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*лфиндтипе*<br/>
Значение, указывающее тип требуемой операции поиска. Вы можете выбрать

- AFX_DAO_NEXT найти следующее расположение совпадающей строки.

- AFX_DAO_PREV найти предыдущее расположение соответствующей строки.

- AFX_DAO_FIRST найти первое расположение соответствующей строки.

- AFX_DAO_LAST найти Последнее расположение соответствующей строки.

*лпсзфилтер*<br/>
Строковое выражение (например, предложение **WHERE** в инструкции SQL без слова **WHERE**), используемое для нахождение записи. Пример:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Вы можете найти первый, следующий, предыдущий или последний экземпляр строки. `Find` является виртуальной функцией, поэтому ее можно переопределить и добавить собственную реализацию. Функции члена `FindFirst`, `FindLast`, `FindNext`и `FindPrev` вызывают функцию члена `Find`, поэтому можно использовать `Find` для управления поведением всех операций поиска.

Чтобы найти запись в наборе записей типа Table, вызовите функцию-член [Seek](#seek) .

> [!TIP]
>  Чем меньше набор записей, тем эффективнее `Find` будет. В целом, и, особенно с данными ODBC, лучше создать новый запрос, извлекающий только нужные записи.

Связанные сведения см. в разделе "FindFirst, FindLast, FindNext, методы Финдпревиаус" справки DAO.

##  <a name="findfirst"></a>CDaoRecordset:: FindFirst

Вызовите эту функцию-член, чтобы найти первую запись, которая соответствует заданному условию.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*лпсзфилтер*<br/>
Строковое выражение (например, предложение **WHERE** в инструкции SQL без слова **WHERE**), используемое для нахождение записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Функция члена `FindFirst` начинает поиск с начала набора записей и выполняет поиск в конце набора записей.

Если вы хотите включить в Поиск все записи (не только те, которые соответствуют определенному условию), используйте одну из операций перемещения, чтобы перейти от записи к записи. Чтобы указать запись в наборе записей типа Table, вызовите функцию-член `Seek`.

Если запись, соответствующая критериям, не найдена, указатель текущей записи не определен, а `FindFirst` возвращает ноль. Если набор записей содержит более одной записи, удовлетворяющей критериям, `FindFirst` находит первое вхождение, `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи не забудьте сохранить изменения, вызвав функцию `Update` члена перед переходом к другой записи. При переходе на другую запись без обновления ваши изменения теряются без предупреждения.

`Find` функции члена выполняют поиск из расположения и в направлении, указанном в следующей таблице:

|Поиск операций|Begin|Направление поиска|
|---------------------|-----------|----------------------|
|`FindFirst`|Начало набора записей|Конец набора записей|
|`FindLast`|Конец набора записей|Начало набора записей|
|`FindNext`|Текущая запись|Конец набора записей|
|`FindPrevious`|Текущая запись|Начало набора записей|

> [!NOTE]
>  При вызове `FindLast`ядро базы данных Microsoft Jet полностью заполняет набор записей перед началом поиска, если это еще не сделано. Первый поиск может занять больше времени, чем последующие операции поиска.

При использовании одной из операций Find не совпадает с вызовом `MoveFirst` или `MoveNext`, но это просто делает первую или следующую запись текущей, не указывая условие. Операцию поиска можно выполнить с помощью операции перемещения.

При использовании операций поиска учитывайте следующее.

- Если `Find` возвращает ненулевое значение, текущая запись не определена. В этом случае необходимо переместить указатель текущей записи обратно на допустимую запись.

- Нельзя использовать операцию Find с прокручиваемым набором записей типа моментальных снимков с прокруткой только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты США ("месяц-день-год"), даже если не используется американская версия ядра СУБД Microsoft Jet. в противном случае соответствующие записи могут не найтися.

- При работе с базами данных ODBC и большими динамическими подмножествами можно обнаружить, что использование операций поиска выполняется очень часто, особенно при работе с большими наборами записей. Производительность можно повысить с помощью запросов SQL с настраиваемыми предложениями **OrderBy** или **WHERE** , запросами параметров или `CDaoQuerydef` объектами, которые извлекают определенные индексированные записи.

Связанные сведения см. в разделе "FindFirst, FindLast, FindNext, методы Финдпревиаус" справки DAO.

##  <a name="findlast"></a>CDaoRecordset:: FindLast

Вызовите эту функцию-член, чтобы найти последнюю запись, соответствующую указанному условию.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*лпсзфилтер*<br/>
Строковое выражение (например, предложение **WHERE** в инструкции SQL без слова **WHERE**), используемое для нахождение записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Функция члена `FindLast` начинает поиск в конце набора записей и осуществляет поиск в обратном направлении к началу набора записей.

Если вы хотите включить в Поиск все записи (не только те, которые соответствуют определенному условию), используйте одну из операций перемещения, чтобы перейти от записи к записи. Чтобы указать запись в наборе записей типа Table, вызовите функцию-член `Seek`.

Если запись, соответствующая критериям, не найдена, указатель текущей записи не определен, а `FindLast` возвращает ноль. Если набор записей содержит более одной записи, удовлетворяющей критериям, `FindFirst` находит первое вхождение, `FindNext` находит следующее вхождение после первого вхождения и т. д.

> [!CAUTION]
>  При изменении текущей записи убедитесь, что изменения сохранены путем вызова функции члена `Update` перед переходом к другой записи. При переходе на другую запись без обновления ваши изменения теряются без предупреждения.

При использовании одной из операций Find не совпадает с вызовом `MoveFirst` или `MoveNext`, но это просто делает первую или следующую запись текущей, не указывая условие. Операцию поиска можно выполнить с помощью операции перемещения.

При использовании операций поиска учитывайте следующее.

- Если `Find` возвращает ненулевое значение, текущая запись не определена. В этом случае необходимо переместить указатель текущей записи обратно на допустимую запись.

- Нельзя использовать операцию Find с прокручиваемым набором записей типа моментальных снимков с прокруткой только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты США ("месяц-день-год"), даже если не используется американская версия ядра СУБД Microsoft Jet. в противном случае соответствующие записи могут не найтися.

- При работе с базами данных ODBC и большими динамическими подмножествами можно обнаружить, что использование операций поиска выполняется очень часто, особенно при работе с большими наборами записей. Производительность можно повысить с помощью запросов SQL с настраиваемыми предложениями **OrderBy** или **WHERE** , запросами параметров или `CDaoQuerydef` объектами, которые извлекают определенные индексированные записи.

Связанные сведения см. в разделе "FindFirst, FindLast, FindNext, методы Финдпревиаус" справки DAO.

##  <a name="findnext"></a>CDaoRecordset:: FindNext

Вызовите эту функцию-член, чтобы найти следующую запись, которая соответствует заданному условию.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*лпсзфилтер*<br/>
Строковое выражение (например, предложение **WHERE** в инструкции SQL без слова **WHERE**), используемое для нахождение записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Функция члена `FindNext` начинает поиск в текущей записи и выполняет поиск в конце набора записей.

Если вы хотите включить в Поиск все записи (не только те, которые соответствуют определенному условию), используйте одну из операций перемещения, чтобы перейти от записи к записи. Чтобы указать запись в наборе записей типа Table, вызовите функцию-член `Seek`.

Если запись, соответствующая критериям, не найдена, указатель текущей записи не определен, а `FindNext` возвращает ноль. Если набор записей содержит более одной записи, удовлетворяющей критериям, `FindFirst` находит первое вхождение, `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи убедитесь, что изменения сохранены путем вызова функции члена `Update` перед переходом к другой записи. При переходе на другую запись без обновления ваши изменения теряются без предупреждения.

При использовании одной из операций Find не совпадает с вызовом `MoveFirst` или `MoveNext`, но это просто делает первую или следующую запись текущей, не указывая условие. Операцию поиска можно выполнить с помощью операции перемещения.

При использовании операций поиска учитывайте следующее.

- Если `Find` возвращает ненулевое значение, текущая запись не определена. В этом случае необходимо переместить указатель текущей записи обратно на допустимую запись.

- Нельзя использовать операцию Find с прокручиваемым набором записей типа моментальных снимков с прокруткой только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты США ("месяц-день-год"), даже если не используется американская версия ядра СУБД Microsoft Jet. в противном случае соответствующие записи могут не найтися.

- При работе с базами данных ODBC и большими динамическими подмножествами можно обнаружить, что использование операций поиска выполняется очень часто, особенно при работе с большими наборами записей. Производительность можно повысить с помощью запросов SQL с настраиваемыми предложениями **OrderBy** или **WHERE** , запросами параметров или `CDaoQuerydef` объектами, которые извлекают определенные индексированные записи.

Связанные сведения см. в разделе "FindFirst, FindLast, FindNext, методы Финдпревиаус" справки DAO.

##  <a name="findprev"></a>CDaoRecordset:: Финдпрев

Вызовите эту функцию-член, чтобы найти предыдущую запись, которая соответствует заданному условию.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*лпсзфилтер*<br/>
Строковое выражение (например, предложение **WHERE** в инструкции SQL без слова **WHERE**), используемое для нахождение записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Функция члена `FindPrev` начинает поиск по текущей записи и осуществляет поиск в обратном направлении к началу набора записей.

Если вы хотите включить в Поиск все записи (не только те, которые соответствуют определенному условию), используйте одну из операций перемещения, чтобы перейти от записи к записи. Чтобы указать запись в наборе записей типа Table, вызовите функцию-член `Seek`.

Если запись, соответствующая критериям, не найдена, указатель текущей записи не определен, а `FindPrev` возвращает ноль. Если набор записей содержит более одной записи, удовлетворяющей критериям, `FindFirst` находит первое вхождение, `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи убедитесь, что изменения сохранены путем вызова функции члена `Update` перед переходом к другой записи. При переходе на другую запись без обновления ваши изменения теряются без предупреждения.

При использовании одной из операций Find не совпадает с вызовом `MoveFirst` или `MoveNext`, но это просто делает первую или следующую запись текущей, не указывая условие. Операцию поиска можно выполнить с помощью операции перемещения.

При использовании операций поиска учитывайте следующее.

- Если `Find` возвращает ненулевое значение, текущая запись не определена. В этом случае необходимо переместить указатель текущей записи обратно на допустимую запись.

- Нельзя использовать операцию Find с прокручиваемым набором записей типа моментальных снимков с прокруткой только вперед.

- При поиске полей, содержащих даты, следует использовать формат даты США ("месяц-день-год"), даже если не используется американская версия ядра СУБД Microsoft Jet. в противном случае соответствующие записи могут не найтися.

- При работе с базами данных ODBC и большими динамическими подмножествами можно обнаружить, что использование операций поиска выполняется очень часто, особенно при работе с большими наборами записей. Производительность можно повысить с помощью запросов SQL с настраиваемыми предложениями **OrderBy** или **WHERE** , запросами параметров или `CDaoQuerydef` объектами, которые извлекают определенные индексированные записи.

Связанные сведения см. в разделе "FindFirst, FindLast, FindNext, методы Финдпревиаус" справки DAO.

##  <a name="getabsoluteposition"></a>CDaoRecordset:: Жетабсолутепоситион

Возвращает номер записи текущей записи объекта набора записей.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Возвращаемое значение

Целое число от 0 до количества записей в наборе записей. Соответствует порядковому номеру текущей записи в наборе записей.

### <a name="remarks"></a>Remarks

Значение свойства примеры AbsolutePosition базового объекта DAO отсчитывается от нуля; значение 0 означает первую запись в наборе записей. Число заполненных записей в наборе записей можно определить, вызвав [жетрекордкаунт](#getrecordcount). Вызов `GetRecordCount` может занять некоторое время, так как он должен получить доступ ко всем записям для определения числа.

Если нет текущей записи, как если бы в наборе записей нет записей, возвращается значение-1. Если текущая запись удалена, значение свойства примеры AbsolutePosition не определено, а MFC создает исключение, если на него есть ссылка. Для наборов записей типа динамического набора новые записи добавляются в конец последовательности.

> [!NOTE]
>  Это свойство не предназначено для использования в качестве номера записи-заместителя. Закладки по-прежнему являются рекомендуемым способом удержания и возврата в заданную точку и являются единственным способом размещения текущей записи для всех типов объектов набора записей. В частности, расположение заданной записи изменяется при удалении записей перед ее удалением. Также нет гарантии того, что данная запись будет иметь ту же абсолютное положение, если набор записей снова создается повторно, так как порядок отдельных записей в наборе записей не гарантируется, если он не создан с помощью инструкции **OrderBy** .

> [!NOTE]
>  Эта функция-член допустима только для наборов записей динамического набора и типа моментального снимка.

Связанные сведения см. в разделе «свойство примеры AbsolutePosition» справки DAO.

##  <a name="getbookmark"></a>CDaoRecordset:: onbookmark

Вызовите эту функцию-член, чтобы получить значение закладки в определенной записи.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, представляющее закладку текущей записи.

### <a name="remarks"></a>Remarks

При создании или открытии объекта набора записей каждая из его записей уже имеет уникальную закладку, если она поддерживается. Вызовите `CanBookmark`, чтобы определить, поддерживает ли набор записей закладки.

Можно сохранить закладку для текущей записи, назначив значение закладки объекту `COleVariant`. Чтобы быстро вернуться к этой записи в любое время после перехода на другую запись, вызовите `SetBookmark` с параметром, соответствующим значению этого `COleVariant` объекта.

> [!NOTE]
>  Вызов метода [Requery](#requery) изменяет закладки DAO.

Связанные сведения см. в разделе "свойство закладки" справки DAO.

##  <a name="getcachesize"></a>CDaoRecordset:: Жеткачесизе

Вызовите эту функцию члена, чтобы получить количество кэшированных записей.

```
long GetCacheSize();
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа, указывающее количество записей в наборе записей динамического набора, содержащего данные, которые должны быть локально кэшированы из источника данных ODBC.

### <a name="remarks"></a>Remarks

Кэширование данных повышает производительность приложения, которое получает данные с удаленного сервера через объекты набора записей динамического типа. Кэш-память — это пространство в локальной памяти, которое содержит данные, наиболее часто извлекаемые с сервера в случае, если данные будут запрошены повторно во время выполнения приложения. При запросе данных ядро СУБД Microsoft Jet сначала проверяет кэш на наличие запрошенных данных, а не получает их с сервера, что занимает больше времени. Данные, не полученные из источника данных ODBC, не сохраняются в кэше.

Любой источник данных ODBC, например присоединенная таблица, может иметь локальный кэш.

Связанные сведения см. в подразделе «CacheSize, свойства Качестарт» справки DAO.

##  <a name="getcachestart"></a>CDaoRecordset:: Жеткачестарт

Вызовите эту функцию члена, чтобы получить значение закладки первой записи в наборе записей для кэширования.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Возвращаемое значение

`COleVariant`, указывающий закладку первой записи в наборе записей для кэширования.

### <a name="remarks"></a>Remarks

Ядро СУБД Microsoft Jet запрашивает записи в диапазоне кэша из кэша и запрашивает записи за пределами диапазона кэша с сервера.

> [!NOTE]
>  Записи, полученные из кэша, не отображают изменения, внесенные одновременно с данными источника другими пользователями.

Связанные сведения см. в подразделе «CacheSize, свойства Качестарт» справки DAO.

##  <a name="getcurrentindex"></a>CDaoRecordset:: Жеткуррентиндекс

Вызовите эту функцию-член, чтобы определить, какой индекс используется в настоящий момент в индексированном табличном типе `CDaoRecordset` объекте.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащая имя индекса, используемого в настоящий момент с набором записей типа Table. Возвращает пустую строку, если индекс не задан.

### <a name="remarks"></a>Remarks

Этот индекс является основанием для упорядочения записей в наборе записей типа Table и используется функцией-членом [Seek](#seek) для поиска записей.

Объект `CDaoRecordset` может иметь более одного индекса, но может использовать только один индекс за раз (хотя для объекта [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md) может быть определено несколько индексов).

Дополнительные сведения см. в разделе "объект индекса" и в определении "текущий индекс" справки DAO.

##  <a name="getdatecreated"></a>CDaoRecordset:: Жетдатекреатед

Вызовите эту функцию-член для получения даты и времени создания базовой таблицы.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий дату и время создания базовой таблицы.

### <a name="remarks"></a>Remarks

Параметры даты и времени наследуются от компьютера, на котором была создана базовая таблица.

Связанные сведения см. в подразделе «DateCreated, свойства LastUpdated» справки DAO.

##  <a name="getdatelastupdated"></a>CDaoRecordset:: Жетдателаступдатед

Вызовите эту функцию члена, чтобы получить дату и время последнего обновления схемы.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий дату и время последнего обновления структуры базовой таблицы (схемы).

### <a name="remarks"></a>Remarks

Параметры даты и времени наследуются от компьютера, на котором была последний раз была обновлена структура базовой таблицы (схема).

Связанные сведения см. в подразделе «DateCreated, свойства LastUpdated» справки DAO.

##  <a name="getdefaultdbname"></a>CDaoRecordset:: Жетдефаултдбнаме

Вызовите эту функцию члена, чтобы определить имя базы данных для этого набора записей.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащий путь и имя базы данных, от которой получен этот набор записей.

### <a name="remarks"></a>Remarks

Если набор записей создается без указателя на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), то этот путь используется набором записей для открытия базы данных по умолчанию. По умолчанию эта функция возвращает пустую строку. Когда ClassWizard наследует новый набор записей от `CDaoRecordset`, он создаст эту функцию.

В следующем примере показано использование двойной обратной косой черты (\\\\) в строке, как требуется для правильной интерпретации строки.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>CDaoRecordset:: GetDefaultSQL

Платформа вызывает эту функцию-член для получения инструкции SQL по умолчанию, на которой основан набор записей.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащая инструкцию SQL по умолчанию.

### <a name="remarks"></a>Remarks

Это может быть имя таблицы или инструкция SQL **SELECT** .

Вы косвенно определяете инструкцию SQL по умолчанию, объявляя класс набора записей с помощью ClassWizard, и ClassWizard выполняет эту задачу.

Если вы передаете пустую строку SQL для [открытия](#open), эта функция вызывается для определения имени таблицы или SQL для набора записей.

##  <a name="geteditmode"></a>CDaoRecordset:: Жетедитмоде

Вызовите эту функцию-член, чтобы определить состояние редактирования, которое может иметь одно из следующих значений:

```
short GetEditMode();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указывающее состояние редактирования для текущей записи.

### <a name="remarks"></a>Remarks

|Значение|Description|
|-----------|-----------------|
|`dbEditNone`|Операции редактирования не выполняются.|
|`dbEditInProgress`|Был вызван метод `Edit`.|
|`dbEditAdd`|Был вызван метод `AddNew`.|

Связанные сведения см. в разделе «свойство EditMode» справки DAO.

##  <a name="getfieldcount"></a>CDaoRecordset:: Жетфиелдкаунт

Вызовите эту функцию-член, чтобы получить количество полей (столбцов), определенных в наборе записей.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число полей в наборе записей.

### <a name="remarks"></a>Remarks

Связанные сведения см. в разделе "свойство Count" справки DAO.

##  <a name="getfieldinfo"></a>CDaoRecordset:: Жетфиелдинфо

Вызовите эту функцию-член для получения сведений о полях в наборе записей.

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

*ниндекс*<br/>
Отсчитываемый от нуля индекс предварительно заданного поля в коллекции полей набора записей для поиска по индексу.

*FieldInfo*<br/>
Ссылка на структуру [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) .

*двинфуптионс*<br/>
Параметры, указывающие, какие сведения о наборе записей необходимо извлечь. Доступные параметры перечислены здесь вместе с тем, что вызывает возврат функции. Для лучшей производительности извлеките только необходимый уровень информации:

- Имя, тип, размер, атрибуты `AFX_DAO_PRIMARY_INFO` (по умолчанию)

- `AFX_DAO_SECONDARY_INFO` первичной информации, а также: порядковый номер, обязательный параметр, разрешить нулевую длину, порядок сортировки, внешний имя, исходное поле, исходную таблицу

- `AFX_DAO_ALL_INFO` первичной и дополнительной информации, плюс: значение по умолчанию, правило проверки, текст проверки

*лпсзнаме*<br/>
Имя поля.

### <a name="remarks"></a>Remarks

Одна версия функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.

Описание возвращаемых сведений см. в разделе Структура [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) . Эта структура содержит элементы, соответствующие элементам приведенных выше данных в описании *двинфуптионс*. При запросе информации на одном уровне вы также получаете сведения для всех предыдущих уровней.

Дополнительные сведения см. в разделе «свойство Attributes» справки DAO.

##  <a name="getfieldvalue"></a>CDaoRecordset:: GetFieldValue

Вызовите эту функцию-член для получения данных в наборе записей.

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

*лпсзнаме*<br/>
Указатель на строку, содержащую имя поля.

*varValue*<br/>
Ссылка на объект `COleVariant`, в котором будет храниться значение поля.

*ниндекс*<br/>
Отсчитываемый от нуля индекс поля в коллекции полей набора записей для поиска по индексу.

### <a name="return-value"></a>Возвращаемое значение

Две версии `GetFieldValue`, возвращающие значение, возвращают объект [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение поля.

### <a name="remarks"></a>Remarks

Можно найти поле по имени или по порядковому номеру.

> [!NOTE]
>  Более эффективно вызывать одну из версий этой функции-члена, которая принимает `COleVariant` ссылку на объект в качестве параметра вместо вызова версии, возвращающей объект `COleVariant`. Последние версии этой функции сохраняются для обеспечения обратной совместимости.

Используйте `GetFieldValue` и [сетфиелдвалуе](#setfieldvalue) для динамической привязки полей во время выполнения, а не для статических привязок столбцов с помощью механизма [DoFieldExchange](#dofieldexchange) .

`GetFieldValue` и механизм `DoFieldExchange` можно сочетать для повышения производительности. Например, используйте `GetFieldValue` для получения значения, которое требуется только по запросу, и назначьте этот вызов кнопке "Дополнительные сведения" в интерфейсе.

Дополнительные сведения см. в разделах «объект поля» и «значение свойства» справки DAO.

##  <a name="getindexcount"></a>CDaoRecordset:: Жетиндекскаунт

Вызовите эту функцию-член, чтобы определить количество индексов, доступных для набора записей типа Table.

```
short GetIndexCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество индексов в наборе записей типа Table.

### <a name="remarks"></a>Remarks

`GetIndexCount` удобно использовать для циклического прохода по всем индексам в наборе записей. Для этой цели используйте `GetIndexCount` в сочетании с [жетиндексинфо](#getindexinfo). При вызове этой функции-члена для наборов записей динамического типа или типа моментального снимка MFC создает исключение.

Дополнительные сведения см. в разделе «свойство Attributes» справки DAO.

##  <a name="getindexinfo"></a>CDaoRecordset:: Жетиндексинфо

Вызовите эту функцию-член, чтобы получить различные виды информации о индексе, определенном в базовой таблице базового набора записей.

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

*ниндекс*<br/>
Отсчитываемый от нуля индекс в коллекции индексов таблицы для поиска по числовой позиции.

*индексинфо*<br/>
Ссылка на структуру [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) .

*двинфуптионс*<br/>
Параметры, указывающие, какие сведения о индексе следует извлечь. Доступные параметры перечислены здесь вместе с тем, что вызывает возврат функции. Для лучшей производительности извлеките только необходимый уровень информации:

- Имя `AFX_DAO_PRIMARY_INFO` (по умолчанию), сведения о поле, поля

- `AFX_DAO_SECONDARY_INFO` первичной информации, а также: основной, уникальный, кластеризованный, Игноренуллс, обязательный, внешний

- `AFX_DAO_ALL_INFO` первичной и дополнительной информации, а также: число различных объектов

*лпсзнаме*<br/>
Указатель на имя объекта индекса, для поиска по имени.

### <a name="remarks"></a>Remarks

Одна версия функции позволяет выполнять поиск индекса по его позиции в коллекции. Другая версия позволяет искать индекс по имени.

Описание возвращаемых сведений см. в разделе Структура [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) . Эта структура содержит элементы, соответствующие элементам приведенных выше данных в описании *двинфуптионс*. При запросе информации на одном уровне вы также получаете сведения для всех предыдущих уровней.

Дополнительные сведения см. в разделе «свойство Attributes» справки DAO.

##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset:: Жетластмодифиедбукмарк

Вызовите эту функцию члена, чтобы получить закладку недавно добавленной или обновленной записи.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

`COleVariant`, содержащая закладку, которая указывает на недавно добавленную или измененную запись.

### <a name="remarks"></a>Remarks

При создании или открытии объекта набора записей каждая из его записей уже имеет уникальную закладку, если она поддерживается. Вызовите метод [Onbookmark](#getbookmark) , чтобы определить, поддерживает ли набор записей закладки. Если набор записей не поддерживает закладки, выдается `CDaoException`.

При добавлении записи она отображается в конце набора записей и не является текущей записью. Чтобы сделать новую запись текущей, вызовите `GetLastModifiedBookmark`, а затем вызовите `SetBookmark`, чтобы вернуться к вновь добавленной записи.

Связанные сведения см. в разделе "свойство LastModified" справки DAO.

##  <a name="getlockingmode"></a>CDaoRecordset:: Жетлоккингмоде

Вызовите эту функцию члена, чтобы определить тип блокировки, действующей для набора записей.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если тип блокировки является пессимистичным, в противном случае — 0 для блокировки оптимистической записи.

### <a name="remarks"></a>Remarks

Когда действует Пессимистическая блокировка, страница данных, содержащая редактируемую запись, блокируется сразу же после вызова функции-члена [Edit](#edit) . Страница разблокируется при вызове функции-члена [Update](#update) или [Close](#close) или любых операций перемещения или поиска.

Если применяется Оптимистическая блокировка, страница данных, содержащая запись, блокируется только во время обновления записи с помощью функции-члена `Update`.

При работе с источниками данных ODBC режим блокировки всегда является оптимистическим.

Дополнительные сведения см. в разделах «Локкедитс Property» и «поведение блокировки в многопользовательских приложениях» справки DAO.

##  <a name="getname"></a>CDaoRecordset:: Name

Вызовите эту функцию члена, чтобы получить имя набора записей.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащая имя набора записей.

### <a name="remarks"></a>Remarks

Имя набора записей должно начинаться с буквы и может содержать не более 40 символов. Оно может содержать цифры и символы подчеркивания, но не может содержать знаки препинания и пробелы.

Связанные сведения см. в разделе "свойство Name" справки DAO.

##  <a name="getparamvalue"></a>CDaoRecordset:: Жетпарамвалуе

Вызовите эту функцию члена, чтобы получить текущее значение указанного параметра, хранящегося в базовом объекте Даопараметер.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Числовое значение параметра в базовом объекте Даопараметер.

*лпсзнаме*<br/>
Имя параметра, значение которого требуется.

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение параметра.

### <a name="remarks"></a>Remarks

Доступ к параметру можно получить по имени или его числовому положению в коллекции.

Дополнительные сведения см. в разделе "объект Parameter" справки DAO.

##  <a name="getpercentposition"></a>CDaoRecordset:: Жетперцентпоситион

При работе с набором записей динамического типа или типа моментального снимка при вызове `GetPercentPosition` до полного заполнения набора записей объем передвижения определяется относительно числа записей, к которым осуществлялся доступ, как указано путем вызова [жетрекордкаунт](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>Возвращаемое значение

Число от 0 до 100, указывающее приблизительное расположение текущей записи в объекте набора записей на основе процента записей в наборе записей.

### <a name="remarks"></a>Remarks

Можно перейти к последней записи, вызвав [MoveLast](#movelast) для завершения заполнения всех наборов записей, но это может занять значительное время.

Можно вызвать `GetPercentPosition` для всех трех типов объектов Recordset, включая таблицы без индексов. Однако нельзя вызвать `GetPercentPosition` для моментальных снимков с прокруткой только вперед или в наборе записей, открытом из сквозного запроса к внешней базе данных. Если текущая запись отсутствует или текущая запись была удалена, создается `CDaoException`.

Связанные сведения см. в разделе «свойство Перцентпоситион» справки DAO.

##  <a name="getrecordcount"></a>CDaoRecordset:: Жетрекордкаунт

Вызовите эту функцию-член, чтобы узнать, сколько записей в наборе записей было получено.

```
long GetRecordCount();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число записей, к которым осуществлялось обращение в объекте Recordset.

### <a name="remarks"></a>Remarks

`GetRecordCount` не указывает, сколько записей содержится в динамическом типе или наборе записей моментального снимка, пока не будут доступны все записи. Для выполнения этого вызова функции-члена может потребоваться значительное время.

После получения доступа к последней записи возвращаемое значение указывает общее число неудаленных записей в наборе записей. Чтобы принудительно получить доступ к последней записи, вызовите функцию члена `MoveLast` или `FindLast` для набора записей. Можно также использовать счетчик SQL для определения приблизительного числа записей, возвращаемых запросом.

Когда приложение удаляет записи в наборе записей динамического типа, возвращаемое значение `GetRecordCount` уменьшается. Однако записи, удаленные другими пользователями, не отражаются `GetRecordCount`, пока текущая запись не будет помещена в удаленную запись. Если выполнить транзакцию, влияющую на число записей, и затем откатить транзакцию, `GetRecordCount` не будет отражать фактическое число оставшихся записей.

Значение `GetRecordCount` из набора записей типа SNAPSHOT не влияет на изменения в базовых таблицах.

Значение `GetRecordCount` из набора записей типа "Таблица" отражает приблизительное количество записей в таблице, и оно затронуто немедленно, так как записи таблицы добавляются и удаляются.

Набор записей без записей возвращает значение 0. При работе с присоединенными таблицами или базами данных ODBC `GetRecordCount` всегда возвращает значение-1. Вызов функции-члена `Requery` в наборе записей сбрасывает значение `GetRecordCount` точно так же, как если бы запрос был выполнен повторно.

Связанные сведения см. в разделе «свойство RecordCount» справки DAO.

##  <a name="getsql"></a>CDaoRecordset:: Жетскл

Вызовите эту функцию члена, чтобы получить инструкцию SQL, которая использовалась для выбора записей набора записей при его открытии.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащая инструкцию SQL.

### <a name="remarks"></a>Remarks

Как правило, это инструкция SQL **SELECT** .

Строка, возвращаемая `GetSQL`, обычно отличается от строки, которая могла быть передана набору записей в параметре *lpszSQL* в функцию [Open](#open) -Member. Это обусловлено тем, что набор записей формирует полную инструкцию SQL на основе того, что вы передали в `Open`, что вы указали в ClassWizard и что вы могли указать в [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) элементов данных.

> [!NOTE]
>  Вызывайте эту функцию члена только после вызова `Open`.

Связанные сведения см. в разделе «свойство SQL» справки DAO.

##  <a name="gettype"></a>CDaoRecordset:: GetType

Вызовите эту функцию члена после открытия набора записей, чтобы определить тип объекта набора записей.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений, указывающее тип набора записей:

- `dbOpenTable` набор записей типа Table

- `dbOpenDynaset` набор записей динамического набора

- `dbOpenSnapshot` набор записей типа "снимок"

### <a name="remarks"></a>Remarks

Связанные сведения см. в разделе "свойство Type" справки DAO.

##  <a name="getvalidationrule"></a>CDaoRecordset:: Жетвалидатионруле

Вызовите эту функцию члена, чтобы определить правило, используемое для проверки данных.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString`, содержащий значение, которое проверяет данные в записи при их изменении или добавлении в таблицу.

### <a name="remarks"></a>Remarks

Это правило основано на тексте и применяется каждый раз при изменении базовой таблицы. Если данные недопустимы, MFC создает исключение. Возвращаемое сообщение об ошибке — это текст свойства Валидатионтекст объекта базового поля, если он указан, или текст выражения, указанного свойством ValidationRule базового объекта Field. Чтобы получить текст сообщения об ошибке, можно вызвать [жетвалидатионтекст](#getvalidationtext) .

Например, поле в записи, для которой требуется день месяца, может иметь правило проверки, например "день от 1 до 31".

Связанные сведения см. в разделе "свойство ValidationRule" справки DAO.

##  <a name="getvalidationtext"></a>CDaoRecordset:: Жетвалидатионтекст

Вызовите эту функцию члена, чтобы получить текст свойства Валидатионтекст базового объекта Field.

```
CString GetValidationText();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString`, содержащий текст сообщения, которое отображается, если значение поля не удовлетворяет правилу проверки базового объекта Field.

### <a name="remarks"></a>Remarks

Связанные сведения см. в разделе «свойство Валидатионтекст» справки DAO.

##  <a name="isbof"></a>CDaoRecordset:: Исбоф

Вызовите эту функцию члена перед прокруткой от записи к записи, чтобы узнать, исчезли ли вы до первой записи набора записей.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или если вы выполнили прокрутку назад перед первой записью; в противном случае — 0.

### <a name="remarks"></a>Remarks

Можно также вызвать `IsBOF` вместе с `IsEOF`, чтобы определить, содержит ли набор записей какие-либо записи или пуст. Сразу после вызова `Open`, если набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, имеющего по крайней мере одну запись, первая запись является текущей, а `IsBOF` возвращает 0.

Если первая запись является текущей и вызывается `MovePrev`, `IsBOF` впоследствии вернет ненулевое значение. Если `IsBOF` возвращает ненулевое значение и вызывается `MovePrev`, возникает исключение. Если `IsBOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, требующее текущей записи, приведет к возникновению исключения.

Воздействие конкретных методов на параметры `IsBOF` и `IsEOF`:

- Вызов `Open*` внутренне делает первую запись в наборе записей текущей записью, вызывая `MoveFirst`. Таким образом, вызов `Open` для пустого набора записей приводит к тому, что `IsBOF` и `IsEOF` возвращают ненулевое значение. (В следующей таблице показано поведение неудачного `MoveFirst` или вызова `MoveLast`.)

- Все операции перемещения, которые успешно находят запись, приводят к тому, что `IsBOF` и `IsEOF` возвращают 0.

- Вызов `AddNew`, за которым следует `Update` вызов, который успешно вставляет новую запись, приведет к тому, что `IsBOF` возвратит 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` будет всегда оставаться неизменным. Как определено ядром СУБД Microsoft Jet, указатель текущей записи пустого набора записей находится в конце файла, поэтому новая запись вставляется после текущей записи.

- Любой вызов `Delete`, даже если удаляет единственную оставшуюся запись из набора записей, не изменит значение `IsBOF` или `IsEOF`.

В этой таблице показано, какие операции перемещения разрешены с различными сочетаниями `IsBOF`/ `IsEOF`.

||MoveFirst, MoveLast|Мовепрев,<br /><br /> Переместить < 0|Переместить 0|Метод<br /><br /> Переместить > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= Ненулевой,<br /><br /> `IsEOF`=0|Разрешено|Исключение|Исключение|Разрешено|
|`IsBOF`=0,<br /><br /> `IsEOF`= ненулевой|Разрешено|Разрешено|Исключение|Исключение|
|Оба ненулевых значения|Исключение|Исключение|Исключение|Исключение|
|Оба значения 0|Разрешено|Разрешено|Разрешено|Разрешено|

Разрешение операции перемещения не означает, что операция успешно найдет запись. Он просто указывает, что попытка выполнить указанную операцию перемещения разрешена и не создаст исключение. Значения функций-членов `IsBOF` и `IsEOF` могут измениться в результате попытки перемещения.

В следующей таблице показан результат операций перемещения, которые не находят запись на значение параметров `IsBOF` и `IsEOF`.

||исбоф|исеоф|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Отличные|Отличные|
|`Move` 0|Без изменения.|Без изменения.|
|`MovePrev`, `Move` < 0|Отличные|Без изменения.|
|`MoveNext`, `Move` > 0|Без изменения.|Отличные|

Связанные сведения см. в разделе «Свойства BOF, EOF» справки DAO.

##  <a name="isdeleted"></a>CDaoRecordset:: isDeleted

Вызовите эту функцию члена, чтобы определить, была ли удалена текущая запись.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей расположен на удаленной записи; в противном случае — 0.

### <a name="remarks"></a>Remarks

Если прокрутить запись к записи и `IsDeleted` возвращает значение TRUE (отличное от нуля), то перед выполнением других операций с набором записей необходимо прокрутить на другую запись.

> [!NOTE]
>  Не нужно проверять состояние Deleted для записей в снимке или наборе записей типа таблицы. Поскольку записи не могут быть удалены из моментального снимка, нет необходимости вызывать `IsDeleted`. Для наборов записей типа Table удаленные записи фактически удаляются из набора записей. После удаления записи пользователем, другим пользователем или в другом наборе записей невозможно прокрутить эту запись назад. Поэтому нет необходимости вызывать `IsDeleted`.

Когда вы удаляете запись из динамического набора, она удаляется из него, и вы не сможете прокрутить эту запись назад. Однако если запись в динамическом наборе удаляется либо другим пользователем, либо из другого набора записей, основанного на той же таблице, `IsDeleted` возвратит значение TRUE при последующей прокрутке этой записи.

Дополнительные сведения см. в разделах «метод Delete», «свойство LastModified» и «свойство EditMode» справки DAO.

##  <a name="iseof"></a>CDaoRecordset:: Исеоф

Вызывайте эту функцию члена при прокрутке записи до записи, чтобы узнать, не выходит ли вы за последнюю запись набора записей.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или прокручивается за последнюю запись; в противном случае — 0.

### <a name="remarks"></a>Remarks

Можно также вызвать `IsEOF`, чтобы определить, содержит ли набор записей какие-либо записи или пуст. Сразу после вызова `Open`, если набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, имеющего по крайней мере одну запись, первая запись является текущей, а `IsEOF` возвращает 0.

Если последняя запись является текущей записью при вызове `MoveNext`, `IsEOF` будет впоследствии возвращать ненулевое значение. Если `IsEOF` возвращает ненулевое значение и вызывается `MoveNext`, возникает исключение. Если `IsEOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, требующее текущей записи, приведет к возникновению исключения.

Воздействие конкретных методов на параметры `IsBOF` и `IsEOF`:

- Вызов `Open` внутренне делает первую запись в наборе записей текущей записью, вызывая `MoveFirst`. Таким образом, вызов `Open` для пустого набора записей приводит к тому, что `IsBOF` и `IsEOF` возвращают ненулевое значение. (В следующей таблице приведены сведения о поведении неудачного `MoveFirst` вызова.)

- Все операции перемещения, которые успешно находят запись, приводят к тому, что `IsBOF` и `IsEOF` возвращают 0.

- Вызов `AddNew`, за которым следует `Update` вызов, который успешно вставляет новую запись, приведет к тому, что `IsBOF` возвратит 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` будет всегда оставаться неизменным. Как определено ядром СУБД Microsoft Jet, указатель текущей записи пустого набора записей находится в конце файла, поэтому новая запись вставляется после текущей записи.

- Любой вызов `Delete`, даже если удаляет единственную оставшуюся запись из набора записей, не изменит значение `IsBOF` или `IsEOF`.

В этой таблице показано, какие операции перемещения разрешены с различными сочетаниями `IsBOF`/ `IsEOF`.

||MoveFirst, MoveLast|Мовепрев,<br /><br /> Переместить < 0|Переместить 0|Метод<br /><br /> Переместить > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= Ненулевой,<br /><br /> `IsEOF`=0|Разрешено|Исключение|Исключение|Разрешено|
|`IsBOF`=0,<br /><br /> `IsEOF`= ненулевой|Разрешено|Разрешено|Исключение|Исключение|
|Оба ненулевых значения|Исключение|Исключение|Исключение|Исключение|
|Оба значения 0|Разрешено|Разрешено|Разрешено|Разрешено|

Разрешение операции перемещения не означает, что операция успешно найдет запись. Он просто указывает, что попытка выполнить указанную операцию перемещения разрешена и не создаст исключение. Значения функций-членов `IsBOF` и `IsEOF` могут измениться в результате попытки перемещения.

В следующей таблице показан результат операций перемещения, которые не находят запись на значение параметров `IsBOF` и `IsEOF`.

||исбоф|исеоф|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Отличные|Отличные|
|`Move` 0|Без изменения.|Без изменения.|
|`MovePrev`, `Move` < 0|Отличные|Без изменения.|
|`MoveNext`, `Move` > 0|Без изменения.|Отличные|

Связанные сведения см. в разделе «Свойства BOF, EOF» справки DAO.

##  <a name="isfielddirty"></a>CDaoRecordset:: Исфиелддирти

Вызовите эту функцию-член, чтобы определить, был ли заданный элемент данных поля динамического набора помечен как "грязный" (измененный).

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, являются ли какие-либо из полей "грязными".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанный элемент данных поля помечен как "грязный"; в противном случае — 0.

### <a name="remarks"></a>Remarks

Данные всех элементов данных "грязных" полей будут переданы в запись в источнике данных при обновлении текущей записи путем вызова функции-члена `Update` `CDaoRecordset` (после вызова метода `Edit` или `AddNew`). С помощью этих знаний можно выполнить дальнейшие действия, например снять пометку элемента данных поля, чтобы пометить столбец, чтобы он не записывался в источник данных.

`IsFieldDirty` реализуется с помощью `DoFieldExchange`.

##  <a name="isfieldnull"></a>CDaoRecordset:: Исфиелднулл

Вызовите эту функцию-член, чтобы определить, помечен ли указанный элемент данных поля набора записей как null.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, имеет ли какое-либо из полей значение null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанный элемент данных поля помечен как null. в противном случае — 0.

### <a name="remarks"></a>Remarks

(В терминологии базы данных значение NULL означает, что значение не имеет значения и не совпадает со значением C++NULL в.) Если элемент данных поля помечен как имеющий значение null, он интерпретируется как столбец текущей записи, для которой нет значения.

> [!NOTE]
>  В некоторых ситуациях использование `IsFieldNull` может быть неэффективным, как показано в следующем примере кода:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  Если используется динамическая привязка записей без наследования от `CDaoRecordset`, обязательно используйте VT_NULL, как показано в примере.

##  <a name="isfieldnullable"></a>CDaoRecordset:: Исфиелднуллабле

Вызовите эту функцию-член, чтобы определить, является ли указанный элемент данных поля обнуляемым (может быть задано значение null). C++ Значение NULL не совпадает со значением NULL, что в терминологии базы данных означает, что не имеет значения.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, имеет ли какое-либо из полей значение null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если заданный элемент данных поля может быть установлен в NULL. в противном случае — 0.

### <a name="remarks"></a>Remarks

Поле, которое не может быть null, должно иметь значение. При попытке установить такое поле в значение null при добавлении или обновлении записи источник данных отклоняет Добавление или обновление, а `Update` создает исключение. Исключение возникает при вызове `Update`, а не при вызове `SetFieldNull`.

##  <a name="isopen"></a>CDaoRecordset:: OnOpen

Вызовите эту функцию-член, чтобы определить, открыт ли набор записей.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция члена объекта набора записей `Open` или `Requery` была ранее вызвана и набор записей не был закрыт. в противном случае — 0.

### <a name="remarks"></a>Remarks

##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: m_bCheckCacheForDirtyFields

Содержит флаг, указывающий, будут ли кэшированные поля автоматически помечены как "грязные" (измененные) и NULL.

### <a name="remarks"></a>Remarks

По умолчанию флаг имеет значение TRUE. Параметр в этом элементе данных управляет всем механизмом двойной буферизации. Если установить для флага значение TRUE, кэширование можно отключить для каждого поля, используя механизм DFX. Если установить для флага значение FALSE, необходимо вызвать `SetFieldDirty` и `SetFieldNull`.

Задайте этот элемент данных перед вызовом `Open`. Этот механизм предназначен главным образом для простоты использования. Производительность может снизиться из-за двойной буферизации полей по мере внесения изменений.

##  <a name="m_nfields"></a>CDaoRecordset:: m_nFields

Содержит количество элементов данных полей в классе набора записей и число столбцов, выбранных набором записей из источника данных.

### <a name="remarks"></a>Remarks

Конструктор для класса набора записей должен инициализировать `m_nFields` с правильным числом полей со статическим связыванием. ClassWizard записывает эту инициализацию при его использовании для объявления класса набора записей. Его также можно записать вручную.

Платформа использует это число для управления взаимодействием между элементами данных поля и соответствующими столбцами текущей записи в источнике данных.

> [!NOTE]
>  Это число должно соответствовать числу выходных столбцов, зарегистрированных в `DoFieldExchange` после вызова `SetFieldType` с параметром `CDaoFieldExchange::outputColumn`.

Можно динамически привязывать столбцы к `CDaoRecordset::GetFieldValue` и `CDaoRecordset::SetFieldValue`. В этом случае не нужно увеличивать число в `m_nFields`, чтобы отразить число вызовов функции DFX в функции члена `DoFieldExchange`.

##  <a name="m_nparams"></a>CDaoRecordset:: m_nParams

Содержит число элементов данных параметров в классе набора записей — количество параметров, передаваемых с помощью запроса набора записей.

### <a name="remarks"></a>Remarks

Если класс набора записей содержит какие – либо элементы данных параметров, конструктор класса должен инициализировать *m_nParams* с правильным числом. Значение *m_nParams* по умолчанию равно 0. При добавлении элементов данных параметров, которые необходимо выполнить вручную, необходимо также вручную добавить инициализацию в конструктор класса, чтобы отразить количество параметров (которое должно быть не меньше количества заполнителей "" в *m_strFilter* или *m_strSort* строке).

Платформа использует этот номер при параметризации запроса набора записей.

> [!NOTE]
>  Это число должно соответствовать числу параметров "params", зарегистрированных в `DoFieldExchange` после вызова `SetFieldType` с параметром `CFieldExchange::param`.

Дополнительные сведения см. в разделе "объект Parameter" справки DAO.

##  <a name="m_pdaorecordset"></a>CDaoRecordset:: m_pDAORecordset

Содержит указатель на интерфейс OLE для объекта набора записей DAO, лежащего в основе объекта `CDaoRecordset`.

### <a name="remarks"></a>Remarks

Используйте этот указатель, если требуется прямой доступ к интерфейсу DAO.

Связанные сведения см. в разделе «объект набора записей» справки DAO.

##  <a name="m_pdatabase"></a>CDaoRecordset:: m_pDatabase

Содержит указатель на объект `CDaoDatabase`, через который набор записей соединяется с источником данных.

### <a name="remarks"></a>Remarks

Эта переменная задается двумя способами. Как правило, при создании объекта набора записей передается указатель на уже открытый объект `CDaoDatabase`. Если вместо этого передается значение NULL, `CDaoRecordset` создает объект `CDaoDatabase` и открывает его. В любом случае `CDaoRecordset` сохраняет указатель в этой переменной.

Обычно не нужно напрямую использовать указатель, хранящийся в `m_pDatabase`. Однако при написании собственных расширений для `CDaoRecordset`может потребоваться использовать указатель. Например, указатель может потребоваться, если вы создаете собственные `CDaoException`.

Связанные сведения см. в разделе «объект базы данных» справки DAO.

##  <a name="m_strfilter"></a>CDaoRecordset:: m_strFilter

Содержит строку, которая используется для создания предложения **WHERE** инструкции SQL.

### <a name="remarks"></a>Remarks

Он не включает в себя зарезервированное слово, **где** можно отфильтровать набор записей. Использование этого члена данных неприменимо к наборам записей табличного типа. Использование `m_strFilter` не влияет на открытие набора записей с помощью указателя `CDaoQueryDef`.

Используйте формат даты США (месяц-день-год) при фильтрации полей, содержащих даты, даже если не используется американская версия ядра СУБД Microsoft Jet. в противном случае данные могут быть отфильтрованы не так, как предполагается.

Дополнительные сведения см. в разделе «свойство Filter» справки DAO.

##  <a name="m_strsort"></a>CDaoRecordset:: m_strSort

Содержит строку, содержащую предложение **OrderBy** инструкции SQL без зарезервированных слов **OrderBy**.

### <a name="remarks"></a>Remarks

Можно сортировать объекты наборов записей динамического набора и типа моментального снимка.

Нельзя сортировать объекты Recordset табличного типа. Чтобы определить порядок сортировки набора записей типа Table, вызовите [сеткуррентиндекс](#setcurrentindex).

Использование *m_strSort* не влияет на открытие набора записей с помощью указателя `CDaoQueryDef`.

Связанные сведения см. в разделе "свойство сортировки" справки DAO.

##  <a name="move"></a>CDaoRecordset:: Move

Вызовите эту функцию члена для размещения записей *лровс* набора записей из текущей записи.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Параметры

*лровс*<br/>
Число записей, которые нужно переместить вперед или назад. Положительные значения перемещаются вперед, ближе к концу набора записей. Отрицательные значения перемещаются назад в направлении к началу.

### <a name="remarks"></a>Remarks

Можно перемещаться вперед или назад. `Move( 1 )` эквивалентна `MoveNext`, а `Move( -1 )` эквивалентна `MovePrev`.

> [!CAUTION]
>  Вызов любой из функций `Move` вызывает исключение, если набор записей не содержит записей. Как правило, вызывайте и `IsBOF`, и `IsEOF` перед операцией перемещения, чтобы определить, содержит ли набор записей какие-либо записи. После вызова `Open` или `Requery`вызовите либо `IsBOF`, либо `IsEOF`.

> [!NOTE]
>  При прокрутке после начала или конца набора записей (`IsBOF` или `IsEOF` возвращает ненулевое значение) вызов `Move` создает исключение `CDaoException`.

> [!NOTE]
>  При вызове любой из функций `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

При вызове `Move` для моментального снимка с прокруткой только вперед параметр *лровс* должен быть положительным целым числом, а закладки не допускаются, поэтому можно перемещаться только вперед.

Чтобы сделать первую, последнюю, следующую или предыдущую запись в наборе записей текущей записи, вызовите функцию-член `MoveFirst`, `MoveLast`, `MoveNext`или `MovePrev`.

Дополнительные сведения см. в разделах «метод Move» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» справки DAO.

##  <a name="movefirst"></a>CDaoRecordset:: MoveFirst

Вызовите эту функцию-член, чтобы сделать первую запись в наборе записей (если таковая имеется) текущей записью.

```
void MoveFirst();
```

### <a name="remarks"></a>Remarks

Не нужно вызывать `MoveFirst` сразу после открытия набора записей. В этот момент первая запись (если она есть) автоматически становится текущей.

> [!CAUTION]
>  Вызов любой из функций `Move` вызывает исключение, если набор записей не содержит записей. Как правило, вызывайте и `IsBOF`, и `IsEOF` перед операцией перемещения, чтобы определить, содержит ли набор записей какие-либо записи. После вызова `Open` или `Requery`вызовите либо `IsBOF`, либо `IsEOF`.

> [!NOTE]
>  При вызове любой из функций `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

Используйте функции `Move` для перехода от записи к записи без применения условия. Используйте операции Find, чтобы найти записи в объекте динамического типа или набора записей моментального снимка, удовлетворяющего определенному условию. Чтобы указать запись в объекте набора записей типа Table, вызовите `Seek`.

Если набор записей ссылается на набор записей типа Table, то перемещение следует за текущим индексом таблицы. Текущий индекс можно задать с помощью свойства index базового объекта DAO. Если текущий индекс не задан, порядок возвращаемых записей не определен.

При вызове `MoveLast` для объекта набора записей, основанного на SQL-запросе или QueryDef, запрос будет принудительно завершен, а объект набора записей будет заполнен полностью.

Невозможно вызвать функцию-член `MoveFirst` или `MovePrev` с помощью моментального снимка с прокруткой только вперед.

Чтобы переместить положение текущей записи в объекте набора записей на определенное число записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «метод Move» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» справки DAO.

##  <a name="movelast"></a>CDaoRecordset:: MoveLast

Вызовите эту функцию-член, чтобы сделать последнюю запись (если таковая имеется) в наборе записей текущей записи.

```
void MoveLast();
```

### <a name="remarks"></a>Remarks

> [!CAUTION]
>  Вызов любой из функций `Move` вызывает исключение, если набор записей не содержит записей. Как правило, вызывайте и `IsBOF`, и `IsEOF` перед операцией перемещения, чтобы определить, содержит ли набор записей какие-либо записи. После вызова `Open` или `Requery`вызовите либо `IsBOF`, либо `IsEOF`.

> [!NOTE]
>  При вызове любой из функций `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

Используйте функции `Move` для перехода от записи к записи без применения условия. Используйте операции Find, чтобы найти записи в объекте динамического типа или набора записей моментального снимка, удовлетворяющего определенному условию. Чтобы указать запись в объекте набора записей типа Table, вызовите `Seek`.

Если набор записей ссылается на набор записей типа Table, то перемещение следует за текущим индексом таблицы. Текущий индекс можно задать с помощью свойства index базового объекта DAO. Если текущий индекс не задан, порядок возвращаемых записей не определен.

При вызове `MoveLast` для объекта набора записей, основанного на SQL-запросе или QueryDef, запрос будет принудительно завершен, а объект набора записей будет заполнен полностью.

Чтобы переместить положение текущей записи в объекте набора записей на определенное число записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «метод Move» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» справки DAO.

##  <a name="movenext"></a>CDaoRecordset:: MoveNext

Вызовите эту функцию члена, чтобы сделать следующую запись в наборе записей текущей записью.

```
void MoveNext();
```

### <a name="remarks"></a>Remarks

Рекомендуется вызвать `IsBOF`, прежде чем пытаться перейти к предыдущей записи. Вызов `MovePrev` приведет к возникновению `CDaoException`, если `IsBOF` возвращает ненулевое значение, что означает, что вы уже прокручелись перед первой записью или не выбрали записи в наборе записей.

> [!CAUTION]
>  Вызов любой из функций `Move` вызывает исключение, если набор записей не содержит записей. Как правило, вызывайте и `IsBOF`, и `IsEOF` перед операцией перемещения, чтобы определить, содержит ли набор записей какие-либо записи. После вызова `Open` или `Requery`вызовите либо `IsBOF`, либо `IsEOF`.

> [!NOTE]
>  При вызове любой из функций `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

Используйте функции `Move` для перехода от записи к записи без применения условия. Используйте операции Find, чтобы найти записи в объекте динамического типа или набора записей моментального снимка, удовлетворяющего определенному условию. Чтобы указать запись в объекте набора записей типа Table, вызовите `Seek`.

Если набор записей ссылается на набор записей типа Table, то перемещение следует за текущим индексом таблицы. Текущий индекс можно задать с помощью свойства index базового объекта DAO. Если текущий индекс не задан, порядок возвращаемых записей не определен.

Чтобы переместить положение текущей записи в объекте набора записей на определенное число записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «метод Move» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» справки DAO.

##  <a name="moveprev"></a>CDaoRecordset:: Мовепрев

Вызовите эту функцию члена, чтобы сделать предыдущую запись в наборе записей текущей записью.

```
void MovePrev();
```

### <a name="remarks"></a>Remarks

Рекомендуется вызвать `IsBOF`, прежде чем пытаться перейти к предыдущей записи. Вызов `MovePrev` приведет к возникновению `CDaoException`, если `IsBOF` возвращает ненулевое значение, что означает, что вы уже прокручелись перед первой записью или не выбрали записи в наборе записей.

> [!CAUTION]
>  Вызов любой из функций `Move` вызывает исключение, если набор записей не содержит записей. Как правило, вызывайте и `IsBOF`, и `IsEOF` перед операцией перемещения, чтобы определить, содержит ли набор записей какие-либо записи. После вызова `Open` или `Requery`вызовите либо `IsBOF`, либо `IsEOF`.

> [!NOTE]
>  При вызове любой из функций `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

Используйте функции `Move` для перехода от записи к записи без применения условия. Используйте операции Find, чтобы найти записи в объекте динамического типа или набора записей моментального снимка, удовлетворяющего определенному условию. Чтобы указать запись в объекте набора записей типа Table, вызовите `Seek`.

Если набор записей ссылается на набор записей типа Table, то перемещение следует за текущим индексом таблицы. Текущий индекс можно задать с помощью свойства index базового объекта DAO. Если текущий индекс не задан, порядок возвращаемых записей не определен.

Невозможно вызвать функцию-член `MoveFirst` или `MovePrev` с помощью моментального снимка с прокруткой только вперед.

Чтобы переместить положение текущей записи в объекте набора записей на определенное число записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «метод Move» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» справки DAO.

##  <a name="open"></a>CDaoRecordset:: Open

Чтобы получить записи для набора записей, необходимо вызвать эту функцию члена.

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

*нопентипе*<br/>
Одно из следующих значений:

- `dbOpenDynaset` набор записей динамического типа с двунаправленной прокруткой. Это значение по умолчанию.

- `dbOpenTable` набор записей типа Table с двунаправленной прокруткой.

- `dbOpenSnapshot` набор записей типа Snapshot с двунаправленной прокруткой.

*lpszSQL*<br/>
Указатель на строку, содержащий один из следующих элементов:

- ПУСТОЙ указатель.

- Имя одного или нескольких tabledef или QueryDef (с разделителями-запятыми).

- Инструкция SQL **SELECT** (при необходимости с предложением SQL **WHERE** или **OrderBy** ).

- Транзитный запрос.

*ноптионс*<br/>
Один или несколько параметров, перечисленных ниже. Значение по умолчанию — 0. Возможны следующие значения:

- `dbAppendOnly` можно добавлять только новые записи (только набор записей динамического набора). Этот параметр означает буквально, что записи могут добавляться только. Классы базы данных MFC ODBC имеют параметр только Append, позволяющий извлекать и добавлять записи.

- `dbForwardOnly` набором записей является моментальный снимок с прокруткой только вперед.

- `dbSeeChanges` создать исключение, если изменяемые данные изменяются другим пользователем.

- `dbDenyWrite` другие пользователи не могут изменять или добавлять записи.

- `dbDenyRead` другие пользователи не могут просматривать записи (только набор записей типа "Таблица").

- `dbReadOnly` просматривать можно только записи; другие пользователи могут изменять их.

- разрешены непоследовательные обновления `dbInconsistent` (только набор записей динамического набора).

- `dbConsistent` разрешены только последовательные обновления (только набор записей типа динамического набора).

> [!NOTE]
>  Константы `dbConsistent` и `dbInconsistent` являются взаимоисключающими. Можно использовать один или другой, но не оба в данном экземпляре `Open`.

*птабледеф*<br/>
Указатель на объект [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md) . Эта версия допустима только для наборов записей типа Table. При использовании этого параметра указатель `CDaoDatabase`, используемый для создания `CDaoRecordset`, не используется. Вместо этого используется база данных, в которой находится объект tabledef.

*пкуеридеф*<br/>
Указатель на объект [кдаокуеридеф](../../mfc/reference/cdaoquerydef-class.md) . Эта версия допустима только для наборов записей динамического типа и типа моментального снимка. При использовании этого параметра указатель `CDaoDatabase`, используемый для создания `CDaoRecordset`, не используется. Вместо этого используется база данных, в которой находится объект QueryDef.

### <a name="remarks"></a>Remarks

Перед вызовом `Open`необходимо создать объект набора записей. Для этого можно использовать следующие способы.

- При создании объекта набора записей передайте указатель на объект `CDaoDatabase`, который уже открыт.

- При создании объекта набора записей передайте указатель на неоткрытый объект `CDaoDatabase`. Набор записей открывает объект `CDaoDatabase`, но не закрывает его при закрытии объекта Recordset.

- При создании объекта набора записей передайте пустой указатель. Объект Recordset вызывает `GetDefaultDBName`, чтобы получить имя Microsoft Access. Открываемый MDB файл. Затем набор записей открывает объект `CDaoDatabase` и остается открытым, пока открыт набор записей. При вызове `Close` для набора записей объект `CDaoDatabase` также закрывается.

    > [!NOTE]
    >  Когда набор записей открывает объект `CDaoDatabase`, он открывает источник данных с неэксклюзивным доступом.

Для версии `Open`, использующей параметр *lpszSQL* , после открытия набора записей можно получить записи одним из нескольких способов. Первый вариант — использовать DFX функции в `DoFieldExchange`. Второй вариант — использовать динамическую привязку путем вызова функции-члена `GetFieldValue`. Эти параметры можно реализовать отдельно или в сочетании. Если они объединены, необходимо вручную передать инструкцию SQL в вызове метода `Open`.

При использовании второй версии `Open`, куда передается объект `CDaoTableDef`, результирующие столбцы будут доступны для привязки через `DoFieldExchange`, а также с помощью механизма DFX и (или) динамического связывания через `GetFieldValue`.

> [!NOTE]
>  Вызвать `Open` можно только с помощью объекта `CDaoTableDef` для наборов записей типа Table.

При использовании третьей версии `Open`, куда передается объект `CDaoQueryDef`, этот запрос будет выполнен, а результирующие столбцы будут доступны для привязки через `DoFieldExchange` и с помощью механизма DFX, а также динамически выполнить привязку через `GetFieldValue`.

> [!NOTE]
>  Вызвать `Open` можно только с помощью объекта `CDaoQueryDef` для наборов записей динамического типа и типа моментального снимка.

Для первой версии `Open`, в которой используется параметр `lpszSQL`, записи выбираются на основе критериев, приведенных в следующей таблице.

|Значение параметра `lpszSQL`|Выбранные записи определяются|Пример|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Строка, возвращенная `GetDefaultSQL`.||
|Разделенный запятыми список из одного или нескольких имен tabledef и/или QueryDef.|Все столбцы, представленные в `DoFieldExchange`.|`"Customer"`|
|**Выберите** столбец-список **из** таблицы-список|Указанные столбцы из указанных объектов tabledef и/или QueryDef.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Обычная процедура заключается в передаче значения NULL в `Open`; в этом случае `Open` вызывает метод `GetDefaultSQL`, переопределяемую функцию-член, ClassWizard создаваемую при создании производного от `CDaoRecordset`класса. Это значение предоставляет имена объектов tabledef и/или QueryDef, указанные в ClassWizard. Вместо этого можно указать другие сведения в параметре *lpszSQL* .

Все, что вы передали, `Open` формирует конечную строку SQL для запроса (строка может содержать предложения **WHERE** и **OrderBy** , добавленные к переданной строке *lpszSQL* ), а затем выполняет запрос. Вы можете проверить созданную строку, вызвав `GetSQL` после вызова `Open`.

Элементы данных поля класса Recordset привязаны к столбцам выбранных данных. Если возвращаются какие бы то ни было записи, первая запись станет текущей.

Если необходимо задать параметры для набора записей, такие как фильтр или сортировка, задайте `m_strSort` или `m_strFilter` после создания объекта набора записей, но перед вызовом `Open`. Если необходимо обновить записи в наборе записей после того, как набор записей уже открыт, вызовите `Requery`.

При вызове `Open` для набора записей динамического типа или типа моментального снимка или если источник данных ссылается на инструкцию SQL или объект tabledef, представляющий присоединенную таблицу, нельзя использовать `dbOpenTable` для аргумента типа. в противном случае MFC выдаст исключение. Чтобы определить, представляет ли объект tabledef присоединенную таблицу, создайте объект [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md) и вызовите его [функцию](../../mfc/reference/cdaotabledef-class.md#getconnect) -член GetObject.

Используйте флаг `dbSeeChanges`, если вы хотите выполнить треппинг изменений, внесенных другим пользователем, или другой программой на компьютере при редактировании или удалении той же записи. Например, если два пользователя начинают изменять одну и ту же запись, первый пользователь вызывает функцию члена `Update`. При вызове `Update` вторым пользователем возникает исключение `CDaoException`. Аналогичным образом, если второй пользователь пытается вызвать `Delete` для удаления записи и он уже был изменен первым пользователем, происходит `CDaoException`.

Как правило, если пользователь получает эту `CDaoException` при обновлении, код должен обновить содержимое полей и получить только что измененные значения. Если исключение возникает в процессе удаления, код может отобразить новые данные записи для пользователя и сообщение, указывающее, что данные были недавно изменены. На этом этапе код может запросить подтверждение того, что пользователь по-прежнему хочет удалить запись.

> [!TIP]
>  Используйте параметр «однонаправленная прокрутка» (`dbForwardOnly`), чтобы повысить производительность, когда приложение выполняет один проход через набор записей, Открытый из источника данных ODBC.

Связанные сведения см. в разделе «метод Опенрекордсет» справки DAO.

##  <a name="requery"></a>CDaoRecordset:: Requery

Вызовите эту функцию-член для перестроения (обновления) набора записей.

```
virtual void Requery();
```

### <a name="remarks"></a>Remarks

Если возвращаются какие бы то ни было записи, первая запись станет текущей.

Чтобы набор записей отражал добавления и удаления, которые вы или другие пользователи применяют к источнику данных, необходимо перестроить набор записей путем вызова `Requery`. Если набор записей является динамическим, он автоматически отражает обновления, внесенные вами или другими пользователями в существующие записи (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать `Requery`, чтобы отразить изменения других пользователей, а также добавления и удаления.

Для динамического или моментального снимка вызовите `Requery` каждый раз, когда требуется перестроить набор записей с помощью значений параметров. Задайте новый фильтр или сортировку, установив [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) перед вызовом `Requery`. Задайте новые параметры, назначив новые значения членам данных параметров перед вызовом `Requery`.

Если попытка перестроения набора записей завершается ошибкой, набор записей закрывается. Перед вызовом `Requery`можно определить, можно ли выполнить повторный запрос к набору записей, вызвав функцию члена [канрестарт](#canrestart) . `CanRestart` не гарантирует, что `Requery` будет выполнена.

> [!CAUTION]
>  Вызовите `Requery` только после вызова `Open`.

> [!NOTE]
>  Вызов метода [Requery](#requery) изменяет закладки DAO.

Невозможно вызвать `Requery` для набора записей динамического типа или моментального снимка, если вызов `CanRestart` возвращает 0, а также не может использоваться в наборе записей типа таблицы.

Если после вызова `Requery`и `IsBOF`, и `IsEOF` возвращают ненулевые значения, запрос не возвращал никаких записей, а набор записей не будет содержать данных.

Связанные сведения см. в разделе «метод Requery» справки DAO.

##  <a name="seek"></a>CDaoRecordset:: Seek

Вызовите эту функцию-член, чтобы нахождение записи в индексированном табличном типе объекта Recordset, удовлетворяющего заданным условиям для текущего индекса, и сделать эту запись текущей записью.

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

*лпсзкомпарисон*<br/>
Одно из следующих строковых выражений: "<", "\<=", "=", "> =" или ">".

*pKey1*<br/>
Указатель на [COleVariant](../../mfc/reference/colevariant-class.md) , значение которого соответствует первому полю в индексе. Обязательный элемент.

*pKey2*<br/>
Указатель на `COleVariant`, значение которого соответствует второму полю в индексе, если оно есть. По умолчанию принимает значение NULL.

*pKey3*<br/>
Указатель на `COleVariant`, значение которого соответствует третьему полю в индексе (при наличии). По умолчанию принимает значение NULL.

*пкэйаррай*<br/>
Указатель на массив вариантов типа. Размер массива соответствует числу полей в индексе.

*нкэйс*<br/>
Целое число, соответствующее размеру массива, который является числом полей в индексе.

> [!NOTE]
>  Не указывайте подстановочные знаки в ключах. Подстановочные знаки приведут к тому, что `Seek` не будут возвращать совпадающие записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если совпадающие записи найдены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Используйте вторую (массивную) версию `Seek` для управления индексами из четырех полей или более.

`Seek` обеспечивает высокопроизводительный Поиск по индексу для наборов записей типа Table. Необходимо задать текущий индекс, вызвав `SetCurrentIndex` перед вызовом `Seek`. Если индекс определяет неуникальное поле ключа или поля, `Seek` находит первую запись, удовлетворяющую критериям. Если индекс не задан, создается исключение.

Обратите внимание, что если вы не создаете набор записей в Юникоде, `COleVariant` объекты должны быть объявлены явно как ANSI. Это можно сделать с помощью формы конструктора [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *лпсзсрк* **,** *втсрк* **)** с *втсрк* Set в `VT_BSTRT` (ANSI) или с помощью функции `COleVariant` [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *лпсзсрк* **,** *втсрк* **)** с параметром *втсрк* , имеющим значение `VT_BSTRT`.

При вызове `Seek`передается одно или несколько значений ключей и оператор сравнения ("<", "\<=", "=", "> =" или ">"). `Seek` выполняет поиск по указанным ключевым полям и находит первую запись, удовлетворяющую критериям, заданным в *лпсзкомпарисон* и *pKey1*. После обнаружения `Seek` возвращает ненулевое значение и делает эту запись текущей. Если `Seek` не удается найти совпадение, `Seek` возвращает ноль, а текущая запись не определена. При непосредственном использовании DAO необходимо явно проверить свойство без совпадения.

Если `lpszComparison` имеет значение "=", "> =" или ">", `Seek` начинается в начале индекса. Если *лпсзкомпарисон* имеет значение "<" или "< =", `Seek` начинается в конце индекса и осуществляет поиск назад, если в конце нет повторяющихся записей индекса. В этом случае `Seek` начинает с произвольной записи между повторяющимися записями индекса в конце индекса.

При использовании `Seek`не обязательно быть текущей записью.

Чтобы найти запись в динамическом наборе записей типа или снимке, удовлетворяющем определенному условию, используйте операции поиска. Чтобы включить все записи, а не только те, которые соответствуют определенному условию, используйте операции перемещения для перехода от записи к записи.

Нельзя вызвать `Seek` для присоединенной таблицы любого типа, так как присоединенные таблицы должны быть открыты как наборы записей динамического типа или моментального снимка. Однако при вызове `CDaoDatabase::Open` для непосредственного открытия устанавливаемой базы данных ISAM можно вызвать `Seek` для таблиц в этой базе данных, хотя производительность может быть мала.

Связанные сведения см. в разделе "метод Seek" справки DAO.

##  <a name="setabsoluteposition"></a>CDaoRecordset:: Сетабсолутепоситион

Задает относительный номер записи текущей записи объекта набора записей.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Параметры

*лпоситион*<br/>
Соответствует порядковому номеру текущей записи в наборе записей.

### <a name="remarks"></a>Remarks

Вызов `SetAbsolutePosition` позволяет разместить указатель текущей записи на определенную запись на основе ее порядкового номера в наборе записей динамического типа или моментального снимка. Номер текущей записи можно также определить, вызвав [жетабсолутепоситион](#getabsoluteposition).

> [!NOTE]
>  Эта функция-член допустима только для наборов записей динамического набора и типа моментального снимка.

Значение свойства примеры AbsolutePosition базового объекта DAO отсчитывается от нуля; значение 0 означает первую запись в наборе записей. Если задать значение, превышающее число заполненных записей, то MFC выдаст исключение. Вы можете определить число заполненных записей в наборе записей, вызвав функцию члена `GetRecordCount`.

Если текущая запись удалена, значение свойства примеры AbsolutePosition не определено, а MFC создает исключение, если на него есть ссылка. Новые записи добавляются в конец последовательности.

> [!NOTE]
>  Это свойство не предназначено для использования в качестве номера записи-заместителя. Закладки по-прежнему являются рекомендуемым способом удержания и возврата к заданной должности и являются единственным способом позиционирования текущей записи для всех типов объектов набора записей, поддерживающих закладки. В частности, расположение заданной записи изменяется при удалении записей перед ее удалением. Также нет гарантии того, что данная запись будет иметь ту же абсолютное положение, если набор записей снова создается повторно, так как порядок отдельных записей в наборе записей не гарантируется, если он не создан с помощью инструкции **OrderBy** .

Связанные сведения см. в разделе «свойство примеры AbsolutePosition» справки DAO.

##  <a name="setbookmark"></a>CDaoRecordset:: Сетбукмарк

Вызовите эту функцию члена, чтобы разместить набор записей в записи, содержащей указанную закладку.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*варбукмарк*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение закладки для определенной записи.

### <a name="remarks"></a>Remarks

При создании или открытии объекта набора записей каждая из его записей уже имеет уникальную закладку. Закладку для текущей записи можно получить, вызвав `GetBookmark` и сохранив значение в объекте `COleVariant`. Позже можно вернуться к этой записи, вызвав `SetBookmark`, используя сохраненное значение закладки.

> [!NOTE]
>  Вызов метода [Requery](#requery) изменяет закладки DAO.

Обратите внимание, что если вы не создаете набор записей в Юникоде, объект `COleVariant` должен быть явно объявлен в кодировке ANSI. Это можно сделать с помощью формы конструктора [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *лпсзсрк* **,** *втсрк* **)** с *втсрк* Set в `VT_BSTRT` (ANSI) или с помощью функции `COleVariant` [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *лпсзсрк* **,** *втсрк* **)** с параметром *втсрк* , имеющим значение `VT_BSTRT`.

Дополнительные сведения см. в подразделах «свойство закладки» и свойства с закладками» справки DAO.

##  <a name="setcachesize"></a>CDaoRecordset:: Сеткачесизе

Вызовите эту функцию члена, чтобы задать число записей для кэширования.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Параметры

*лсизе*<br/>
Указывает количество записей. Типичное значение — 100. Значение 0 отключает кэширование. Значение параметра должно составлять от 5 до 1200 записей. Кэш может использовать значительный объем памяти.

### <a name="remarks"></a>Remarks

Кэш-память — это пространство в локальной памяти, которое содержит данные, наиболее часто извлекаемые с сервера в случае, если данные будут запрошены повторно во время выполнения приложения. Кэширование данных повышает производительность приложения, которое получает данные с удаленного сервера через объекты набора записей динамического типа. При запросе данных ядро СУБД Microsoft Jet сначала проверяет кэш на наличие запрошенных данных, а не получает их с сервера, что занимает больше времени. Данные, не полученные из источника данных ODBC, не сохраняются в кэше.

Любой источник данных ODBC, например присоединенная таблица, может иметь локальный кэш. Чтобы создать кэш, откройте объект набора записей из удаленного источника данных, вызовите функции-члены `SetCacheSize` и `SetCacheStart`, а затем вызовите функцию-член `FillCache` или пошаговое выполнение записей с помощью одной из операций перемещения. Параметр *лсизе* функции члена `SetCacheSize` может быть основан на числе записей, с которыми приложение может работать одновременно. Например, если набор записей используется в качестве источника данных, отображаемых на экране, можно передать параметр `SetCacheSize` *лсизе* в виде 20, чтобы отобразить 20 записей за один раз.

Связанные сведения см. в подразделе «CacheSize, свойства Качестарт» справки DAO.

##  <a name="setcachestart"></a>CDaoRecordset:: Сеткачестарт

Вызовите эту функцию члена, чтобы указать закладку первой записи в наборе записей для кэширования.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*варбукмарк*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) , указывающий закладку первой записи в наборе записей для кэширования.

### <a name="remarks"></a>Remarks

Можно использовать значение закладки любой записи для параметра *варбукмарк* функции члена `SetCacheStart`. Создайте запись, которая будет запускать кэш с текущей записью, установите закладку для этой записи с помощью [сетбукмарк](#setbookmark)и передайте значение закладки в качестве параметра функции-члена `SetCacheStart`.

Ядро СУБД Microsoft Jet запрашивает записи в диапазоне кэша из кэша и запрашивает записи за пределами диапазона кэша с сервера.

Записи, полученные из кэша, не отображают изменения, внесенные одновременно с данными источника другими пользователями.

Чтобы принудительно обновить все кэшированные данные, передайте параметр *лсизе* `SetCacheSize` как 0, вызовите `SetCacheSize` еще раз, указав размер кэша, который вы запросили ранее, а затем вызовите функцию `FillCache` члена.

Обратите внимание, что если вы не создаете набор записей в Юникоде, объект `COleVariant` должен быть явно объявлен в кодировке ANSI. Это можно сделать с помощью формы конструктора [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *лпсзсрк* **,** *втсрк* **)** с *втсрк* Set в `VT_BSTRT` (ANSI) или с помощью функции `COleVariant` [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *лпсзсрк* **,** *втсрк* **)** с параметром *втсрк* , имеющим значение `VT_BSTRT`.

Связанные сведения см. в разделе CacheSize, Качестарт Properties (свойства) справки DAO.

##  <a name="setcurrentindex"></a>CDaoRecordset:: Сеткуррентиндекс

Вызовите эту функцию-член, чтобы задать индекс для набора записей типа таблицы.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*лпсзиндекс*<br/>
Указатель, содержащий имя индекса, который необходимо задать.

### <a name="remarks"></a>Remarks

Записи в базовых таблицах не хранятся в определенном порядке. Задание индекса изменяет порядок записей, возвращаемых из базы данных, но не влияет на порядок хранения записей. Указанный индекс уже должен быть определен. При попытке использовать несуществующий объект индекса или если индекс не задан при вызове [Seek](#seek), MFC создает исключение.

Можно создать новый индекс для таблицы, вызвав [кдаотабледеф:: CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) и добавив новый индекс в коллекцию индексов базового объекта tabledef, вызвав [Кдаотабледеф:: Append](../../mfc/reference/cdaotabledef-class.md#append), а затем повторно открыв набор записей.

Записи, возвращаемые из набора записей типа Table, могут упорядочиваться только по индексам, определенным для базового tabledef. Чтобы отсортировать записи в каком-либо другом порядке, можно открыть набор записей динамического типа или типа моментального снимка с помощью предложения **OrderBy** SQL, хранящегося в [CDaoRecordset:: m_strSort](#m_strsort).

Дополнительные сведения см. в разделе "объект индекса" и в определении "текущий индекс" справки DAO.

##  <a name="setfielddirty"></a>CDaoRecordset:: Сетфиелддирти

Вызовите эту функцию-член, чтобы пометить элемент данных поля набора записей как измененный или как неизмененный.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, все элементы данных полей в наборе записей помечаются как помеченные. (C++ Значение NULL не совпадает со значением NULL в терминологии базы данных, что означает отсутствие значения.)

*бдирти*<br/>
Значение TRUE, если элемент данных поля должен быть помечен как "грязный" (измененный). В противном случае FALSE, если элемент данных поля должен быть помечен как "чистый" (без изменений).

### <a name="remarks"></a>Remarks

Пометка полей как неизмененных гарантирует, что поле не будет обновлено.

Платформа помечает измененные элементы данных поля, чтобы убедиться, что они будут записаны в запись в источнике данных с помощью механизма обмена полями записей DAO (DFX). Изменение значения поля обычно автоматически устанавливает поле "грязный", поэтому вам редко приходится вызывать `SetFieldDirty` самостоятельно, но иногда может потребоваться обеспечить явное обновление или вставку столбцов независимо от значения в элементе данных поля. Механизм DFX также использует ПСЕУДОНУЛЛ. Дополнительные сведения см. в разделе [кдаофиелдексчанже:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если механизм двойной буферизации не используется, то изменение значения поля не приводит к автоматическому заданию поля как «грязное». В этом случае необходимо явно задать для поля значение «грязный». Флаг, содержащийся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) , управляет этой автоматической проверкой полей.

> [!NOTE]
>  Вызывайте эту функцию члена только после вызова [Edit](#edit) или [AddNew](#addnew).

Использование значения NULL для первого аргумента функции приведет к применению функции ко всем `outputColumn` полям, а не к полям **param** в `CDaoFieldExchange`. Например, вызов

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

задаст значения NULL только для `outputColumn` полей; поля **параметров** не затрагиваются.

Для работы с **параметром**необходимо указать фактический адрес отдельного **параметра** , с которым вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Это означает, что нельзя установить для всех полей **param** значение null, как это можно сделать с `outputColumn` полями.

`SetFieldDirty` реализуется с помощью `DoFieldExchange`.

##  <a name="setfieldnull"></a>CDaoRecordset:: Сетфиелднулл

Вызовите эту функцию-член, чтобы пометить элемент данных поля набора записей как null (без значения) или как значение, отличное от NULL.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, все элементы данных полей в наборе записей помечаются как помеченные. (C++ Значение NULL не совпадает со значением NULL в терминологии базы данных, что означает отсутствие значения.)

*бнулл*<br/>
Ненулевое значение, если элемент данных поля должен быть помечен как не имеющий значения (null). В противном случае 0, если элемент данных поля должен быть помечен как не равный null.

### <a name="remarks"></a>Remarks

`SetFieldNull` используется для полей, привязанных к механизму `DoFieldExchange`.

При добавлении новой записи в набор записей все элементы данных полей изначально устанавливаются в значение NULL и помечаются как "грязные" (изменено). При извлечении записи из источника данных ее столбцы либо уже имеют значения, либо имеют значение null. Если не нужно делать поле пустым, создается исключение [кдаоексцептион](../../mfc/reference/cdaoexception-class.md) .

Если используется механизм двойной буферизации, например, если вы хотите назначить поле текущей записи без значения, вызовите `SetFieldNull` с параметром *бнулл* , ИМЕЮЩИМ значение true, чтобы пометить его как null. Если поле ранее было отмечено как null, и теперь нужно присвоить ему значение, просто задайте его новое значение. Нет необходимости удалять флаг NULL с `SetFieldNull`. Чтобы определить, может ли поле иметь значение null, вызовите [исфиелднуллабле](#isfieldnullable).

Если механизм двойной буферизации не используется, то при изменении значения поля поле автоматически не задается как «грязный» и не равный null. Необходимо специально задать поля "грязный" и не NULL. Флаг, содержащийся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) , управляет этой автоматической проверкой полей.

Механизм DFX использует ПСЕУДОНУЛЛ. Дополнительные сведения см. в разделе [кдаофиелдексчанже:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
>  Вызывайте эту функцию члена только после вызова [Edit](#edit) или [AddNew](#addnew).

Использование значения NULL для первого аргумента функции приведет к применению функции только к `outputColumn` полям, а не к полям **param** в `CDaoFieldExchange`. Например, вызов

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

задаст значения NULL только для `outputColumn` полей; поля **параметров** не затрагиваются.

##  <a name="setfieldvalue"></a>CDaoRecordset:: Сетфиелдвалуе

Вызовите эту функцию-член, чтобы задать значение поля либо по порядковому номеру, либо путем изменения значения строки.

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

*лпсзнаме*<br/>
Указатель на строку, содержащую имя поля.

*varValue*<br/>
Ссылка на объект [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение содержимого поля.

*ниндекс*<br/>
Целое число, представляющее порядковый номер поля в коллекции полей набора записей (от нуля).

*лпсзвалуе*<br/>
Указатель на строку, содержащую значение содержимого поля.

### <a name="remarks"></a>Remarks

Используйте `SetFieldValue` и [GetFieldValue](#getfieldvalue) для динамической привязки полей во время выполнения, а не для статических привязок столбцов с помощью механизма [DoFieldExchange](#dofieldexchange) .

Обратите внимание, что если вы не создаете набор записей в Юникоде, необходимо либо использовать форму `SetFieldValue`, которая не содержит параметр `COleVariant`, либо объект `COleVariant` должен быть явно объявлен как ANSI. Это можно сделать с помощью формы конструктора [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *лпсзсрк* **,** *втсрк* **)** с *втсрк* Set в `VT_BSTRT` (ANSI) или с помощью функции `COleVariant` [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *лпсзсрк* **,** *втсрк* **)** с параметром *втсрк* , имеющим значение `VT_BSTRT`.

Дополнительные сведения см. в разделах «объект поля» и «значение свойства» справки DAO.

##  <a name="setfieldvaluenull"></a>CDaoRecordset:: Сетфиелдвалуенулл

Вызовите эту функцию-член, чтобы присвоить полю значение null.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс поля в наборе записей для поиска по индексу, начинающемся с нуля.

*лпсзнаме*<br/>
Имя поля в наборе записей для поиска по имени.

### <a name="remarks"></a>Remarks

C++Значение NULL не совпадает со значением NULL, что в терминологии базы данных означает отсутствие значения.

Дополнительные сведения см. в разделах «объект поля» и «значение свойства» справки DAO.

##  <a name="setlockingmode"></a>CDaoRecordset:: Сетлоккингмоде

Вызовите эту функцию члена, чтобы задать тип блокировки для набора записей.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Параметры

*бпессимистик*<br/>
Флаг, указывающий тип блокировки.

### <a name="remarks"></a>Remarks

Когда действует Пессимистическая блокировка, страница 2000, содержащая редактируемую запись, блокируется сразу же после вызова функции-члена `Edit`. Страница разблокируется при вызове функции-члена `Update` или `Close` или любых операций перемещения или поиска.

Если применяется Оптимистическая блокировка, то страница 2000, содержащая запись, блокируется только в тот момент, когда запись обновляется с помощью функции-члена `Update`.

Если страница заблокирована, другие пользователи не могут изменять записи на этой странице. Если вызвать `SetLockingMode` и передать ненулевое значение, а другой пользователь уже заблокировал страницу, при вызове `Edit`возникает исключение. Другие пользователи могут считывать данные с заблокированных страниц.

При вызове `SetLockingMode` с нулевым значением и последующем вызове `Update`, пока страница заблокирована другим пользователем, возникает исключение. Чтобы просмотреть изменения, внесенные в запись другим пользователем (и потерять изменения), вызовите функцию-член `SetBookmark` с значением закладки текущей записи.

При работе с источниками данных ODBC режим блокировки всегда является оптимистическим.

##  <a name="setparamvalue"></a>CDaoRecordset:: Сетпарамвалуе

Вызовите эту функцию-член, чтобы задать значение параметра в наборе записей во время выполнения.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Числовое значение параметра в коллекции параметров объекта QueryDef.

*var*<br/>
Заданное значение; см. раздел Примечания.

*лпсзнаме*<br/>
Имя параметра, значение которого необходимо задать.

### <a name="remarks"></a>Remarks

Параметр должен быть уже установлен в составе строки SQL набора записей. Доступ к параметру можно получить по имени или по позиции индекса в коллекции.

Укажите значение, устанавливаемое в качестве объекта `COleVariant`. Сведения о настройке требуемого значения и типа в объекте `COleVariant` см. в разделе Class [COleVariant](../../mfc/reference/colevariant-class.md). Обратите внимание, что если вы не создаете набор записей в Юникоде, объект `COleVariant` должен быть явно объявлен в кодировке ANSI. Это можно сделать с помощью формы конструктора [COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *лпсзсрк* **,** *втсрк* **)** с *втсрк* Set в `VT_BSTRT` (ANSI) или с помощью функции `COleVariant` [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *лпсзсрк* **,** *втсрк* **)** с параметром *втсрк* , имеющим значение `VT_BSTRT`.

##  <a name="setparamvaluenull"></a>CDaoRecordset:: Сетпарамвалуенулл

Вызовите эту функцию-член, чтобы присвоить параметру значение null.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс поля в наборе записей для поиска по индексу, начинающемся с нуля.

*лпсзнаме*<br/>
Имя поля в наборе записей для поиска по имени.

### <a name="remarks"></a>Remarks

C++Значение NULL не совпадает со значением NULL, что в терминологии базы данных означает отсутствие значения.

##  <a name="setpercentposition"></a>CDaoRecordset:: Сетперцентпоситион

Вызовите эту функцию-член, чтобы задать значение, которое изменяет приближенное расположение текущей записи в объекте набора записей на основе процента записей в наборе записей.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Параметры

*фпоситион*<br/>
Число от 0 до 100.

### <a name="remarks"></a>Remarks

При работе с динамическим типом или набором записей типа snapshot сначала заполните набор записей, переместив его в последнюю запись перед вызовом `SetPercentPosition`. При вызове `SetPercentPosition` до полного заполнения набора записей объем передвижения определяется относительно количества записей, к которым осуществлялся доступ, как указано значением [жетрекордкаунт](#getrecordcount). Можно перейти к последней записи, вызвав `MoveLast`.

После вызова `SetPercentPosition`запись в приблизительном положении, соответствующем этому значению, станет текущей.

> [!NOTE]
>  Не рекомендуется вызывать `SetPercentPosition` для перемещения текущей записи в определенную запись в наборе записей. Вместо этого вызовите функцию члена [сетбукмарк](#setbookmark) .

Связанные сведения см. в разделе «свойство Перцентпоситион» справки DAO.

##  <a name="update"></a>CDaoRecordset:: Update

Вызовите эту функцию-член после вызова функции-члена `AddNew` или `Edit`.

```
virtual void Update();
```

### <a name="remarks"></a>Remarks

Этот вызов необходим для завершения операции `AddNew` или `Edit`.

И `AddNew`, и `Edit` подготавливают буфер редактирования, в котором добавленные или измененные данные помещаются для сохранения в источнике данных. `Update` сохраняет данные. Обновляются только поля, помеченные или обнаруженные как измененные.

Если источник данных поддерживает транзакции, можно сделать вызов `Update` (и соответствующего `AddNew` или `Edit` вызов) транзакции.

> [!CAUTION]
> При вызове `Update` без предварительного вызова `AddNew` или `Edit``Update` создает исключение `CDaoException`. При вызове `AddNew` или `Edit`необходимо вызвать `Update` перед вызовом [MoveNext](#movenext) или закрыть либо набор записей, либо соединение с источником данных. В противном случае изменения будут потеряны без уведомления.

Если объект Recordset пессимистикалли заблокирован в многопользовательской среде, запись остается заблокированной с момента времени, `Edit` используется до завершения обновления. Если набор записей вызывает заблокирован, запись блокируется и сравнивается с предварительно измененной записью непосредственно перед ее обновлением в базе данных. Если запись изменилась с момента вызова `Edit`, операция `Update` завершается сбоем и MFC создает исключение. Режим блокировки можно изменить с помощью `SetLockingMode`.

> [!NOTE]
> Оптимистическая блокировка всегда используется во внешних форматах базы данных, таких как ODBC и installed ISAM.

Дополнительные сведения см. в подразделах "метод AddNew", "метод CancelUpdate", "метод удаления", "свойство LastModified", "метод обновления" и "свойство EditMode" справки DAO.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)<br/>
