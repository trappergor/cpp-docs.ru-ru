---
title: Класс CDaoRecordset | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08e5433cfd7d1627babb4750c94396602a8f276c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400540"
---
# <a name="cdaorecordset-class"></a>Класс CDaoRecordset

Представляет набор записей, выбранных из источника данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Создает объект `CDaoRecordset`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::AddNew](#addnew)|Подготавливает для добавления новой записи. Вызовите [обновления](#update) для завершения добавления.|
|[CDaoRecordset::CanAppend](#canappend)|Возвращает ненулевое значение, если новые записи добавляются в набор записей с помощью [AddNew](#addnew) функция-член.|
|[CDaoRecordset::CanBookmark](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Отменяет все ожидающие обновления из-за [изменить](#edit) или [AddNew](#addnew) операции.|
|[CDaoRecordset::CanRestart](#canrestart)|Возвращает ненулевое значение, если [Requery](#requery) может вызываться для повторного запуска запроса набора записей.|
|[CDaoRecordset::CanScroll](#canscroll)|Возвращает ненулевое значение, если можно прокручивать записи.|
|[CDaoRecordset::CanTransact](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|
|[CDaoRecordset::CanUpdate](#canupdate)|Возвращает ненулевое значение, если можно обновить набор записей (можно добавить, обновить или удалить записи).|
|[CDaoRecordset::Close](#close)|Закрывает набор записей.|
|[CDaoRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. Необходимо явно перейти к другой записи после удаления.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Реализует DAO обмен полями записей (DFX).|
|[CDaoRecordset::Edit](#edit)|Подготавливает для изменения текущей записи. Вызовите `Update` для завершения редактирования.|
|[CDaoRecordset::FillCache](#fillcache)|Заполняет все или часть локального кэша для объекта набора записей, который содержит данные из источника данных ODBC.|
|[CDaoRecordset::Find](#find)|Находит первый, следующего, предыдущего или последнего расположение определенной строки в наборе записей динамического типа, который удовлетворяет указанным критериям и делает этот записи текущей записи.|
|[CDaoRecordset::FindFirst](#findfirst)|Находит первую запись типа динамического или набора записей типа, удовлетворяющей указанным критериям и делает этот записи текущей записи.|
|[CDaoRecordset::FindLast](#findlast)|Находит последнюю запись типа динамического или набора записей типа, удовлетворяющей указанным критериям и делает этот записи текущей записи.|
|[CDaoRecordset::FindNext](#findnext)|Находит следующей записи типа динамического или набора записей типа, удовлетворяющей указанным критериям и делает этот записи текущей записи.|
|[CDaoRecordset::FindPrev](#findprev)|Находит предыдущей записи типа динамического или набора записей типа, удовлетворяющей указанным критериям и делает этот записи текущей записи.|
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Возвращает номер текущей записи в объект набора записей.|
|[CDaoRecordset::GetBookmark](#getbookmark)|Возвращает значение, представляющее закладку на запись.|
|[CDaoRecordset::GetCacheSize](#getcachesize)|Возвращает значение, указывающее количество записей в наборе записей динамического типа, содержащий данные, локально кэшировать из источника данных ODBC.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|Возвращает значение, указывающее закладки для первой записи в наборе записей должен быть помещен в кэш.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Возвращает `CString` , содержащая имя индекса наиболее недавно используется на индексированные табличный тип `CDaoRecordset`.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Возвращает дату и время в базовой таблице базовый `CDaoRecordset` был создан объект|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенные в структуру базовой таблицы, расположенных `CDaoRecordset` объекта.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Возвращает имя источника данных по умолчанию.|
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Вызывается, чтобы получить строку SQL по умолчанию для выполнения.|
|[CDaoRecordset::GetEditMode](#geteditmode)|Возвращает значение, указывающее состояние редактирования для текущей записи.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее количество полей в наборе записей.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Возвращает сведения о полях определенных типов в наборе записей.|
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|Возвращает число индексов в таблице набор записей.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Возвращает различные сведения об индексе.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Используется для определения наиболее недавно добавленных или обновленных записей.|
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Возвращает значение, указывающее тип блокировки, которая действует во время редактирования.|
|[CDaoRecordset::GetName](#getname)|Возвращает `CString` , содержащая имя набора записей.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|Извлекает текущее значение указанного параметра, сохраненного в используемом объекте-DAOParameter.|
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Возвращает позицию текущей записи в процентах от общее количество записей.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Возвращает количество записей, доступных в объекте набора записей.|
|[CDaoRecordset::GetSQL](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|
|[CDaoRecordset::GetType](#gettype)|Вызывается, чтобы определить тип набора записей: тип таблицы, добавляющий или тип моментального снимка.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Возвращает `CString` содержащий значение, которое проверяет данные, вводимые в поле.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Извлекает текст, отображаемый, когда правило проверки не выполняется.|
|[CDaoRecordset::IsBOF](#isbof)|Возвращает ненулевое значение, если набор записей позиционирует перед первой записью. Отсутствует текущая запись.|
|[CDaoRecordset::IsDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей позиционируется в удаленной записи.|
|[CDaoRecordset::IsEOF](#iseof)|Возвращает ненулевое значение, если набор записей позиционирует после последней записи. Отсутствует текущая запись.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи был изменен.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение Null, (при необходимости нет значения).|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи может иметь значение Null (значение не имеющая).|
|[CDaoRecordset::IsOpen](#isopen)|Возвращает ненулевое значение, если [откройте](#open) уже был вызван ранее.|
|[CDaoRecordset::Move](#move)|Устанавливает набор записей на указанное количество записей из текущей записи в любом направлении.|
|[CDaoRecordset::MoveFirst](#movefirst)|Помещает текущей записи на первой записи в наборе записей.|
|[CDaoRecordset::MoveLast](#movelast)|Помещает текущей записи на последней записи в наборе записей.|
|[CDaoRecordset::MoveNext](#movenext)|Помещает текущей записи на следующей записи в наборе записей.|
|[CDaoRecordset::MovePrev](#moveprev)|Помещает текущей записи на предыдущей записи в наборе записей.|
|[CDaoRecordset::Open](#open)|Создает новый набор записей из таблицы, динамический или статический.|
|[CDaoRecordset::Requery](#requery)|Выполняет запрос набора записей, еще раз, чтобы обновить выбранные записи.|
|[CDaoRecordset::Seek](#seek)|Находит записи в объекте набора записей индексированных тип таблицы, удовлетворяющий указанному условию для текущего индекса и делает этот записи текущей записи.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Задает номер текущей записи в объект набора записей.|
|[CDaoRecordset::SetBookmark](#setbookmark)|Устанавливает набор записей на запись, содержащую указанную закладку.|
|[CDaoRecordset::SetCacheSize](#setcachesize)|Задает значение, указывающее количество записей в наборе записей динамического типа, содержащий данные, локально кэшировать из источника данных ODBC.|
|[CDaoRecordset::SetCacheStart](#setcachestart)|Задает значение, указывающее закладки для первой записи в наборе записей должен быть помещен в кэш.|
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Вызывается для задания индекса на набор записей типа таблицы.|
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Помечает указанного поля в текущей записи, как измененный.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Задает значение указанного поля в текущей записи в значение Null (значение не имеющая).|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Задает значение поля в наборе записей.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Задает значение поля в наборе записей, значение Null. (имеющая нет значения).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Задает значение, указывающее тип блокировки для изменения вступают в силу во время редактирования.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|Задает текущее значение указанного параметра, сохраненного в используемом объекте-DAOParameter|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Задает текущее значение указанного параметра в значение Null (значение не имеющая).|
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Задает позицию текущей записи в расположение, соответствующее процент общее число записей в наборе записей.|
|[CDaoRecordset::Update](#update)|Завершает `AddNew` или `Edit` операции путем сохранения новых или измененных данных в источнике данных.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Содержит флаг, указывающее, является ли поля автоматически помечаются как измененный.|
|[CDaoRecordset::m_nFields](#m_nfields)|Содержит число элементов данных полей в классе наборов записей и количество столбцов, выбранных в набор записей из источника данных.|
|[CDaoRecordset::m_nParams](#m_nparams)|Содержит количество элементов данных параметров в классе записей — число параметров, переданных с запросом набора записей|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Указатель на интерфейс DAO, основного объекта набора записей.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Базы данных-источника для данного результирующего набора. Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.|
|[CDaoRecordset::m_strFilter](#m_strfilter)|Содержит строку, используемую для создания SQL **ГДЕ** инструкции.|
|[CDaoRecordset::m_strSort](#m_strsort)|Содержит строку, используемую для создания SQL **ORDER BY** инструкции.|

## <a name="remarks"></a>Примечания

Известный как «набора записей» `CDaoRecordset` объекты доступны в трех следующих форм:

- Наборы записей табличный тип представления базовой таблицы, можно использовать для проверки, добавить, изменить или удалить записи из одной таблицы базы данных.

- Наборы записей типа динамического получены в результате запроса, который может иметь обновляемых записей. Эти наборы записей представляют собой набор записей, которые можно использовать для проверки, добавления, изменения или удаления записей в базовой таблице или таблицах. Наборы записей типа динамического может содержать поля из одной или нескольких таблиц в базе данных.

- Наборы записей типа являются копией статический набор записей, которые можно использовать для поиска данных или создавать отчеты. Эти наборы записей могут содержать поля из одной или нескольких таблиц в базе данных, но не может быть обновлен.

Каждая форма набора записей представляет набор записей, составляет при открытии набора записей. При переходе к записи в набор записей таблицы type или набор записей типа динамического влияют изменения, внесенные в запись после открытия набора записей других пользователей или других наборов записей в приложении. (Не удается обновить набор записей типа.) Можно использовать `CDaoRecordset` напрямую или являются производными класс набора записей для конкретного приложения из `CDaoRecordset`. После этого можно:

- Просмотрите записи.

- Значение индекса и быстро находить для записей с помощью [Seek](#seek) (только для записей типа таблицы).

- Найти записи на основании сравнения строк: «< «,»\<=», «=», «> =», или «>» (копирование и наборы записей типа).

- Обновите записи и укажите режим блокировки (за исключением записей типа снимка).

- Фильтровать набор записей, чтобы ограничить записи, которые он выбирает из доступных в источнике данных.

- Сортировка набора записей.

- Параметризация набора записей для настройки его выбора с информацией, не известных до времени выполнения.

Класс `CDaoRecordset` предоставляет интерфейс аналогичен класс `CRecordset`. Основное различие заключается в этом классе `CDaoRecordset` обращается к данным через доступ объект данным (DAO) основании OLE. Класс `CRecordset` обращается к СУБД через Open Database Connectivity (ODBC) и драйвер ODBC для этого СУБД.

> [!NOTE]
> Классы баз данных DAO, отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. классы DAO обычно предлагают превосходные возможности, поскольку они определяются в ядре СУБД Microsoft Jet.

Вы можете использовать `CDaoRecordset` напрямую или являются производными от класса `CDaoRecordset`. Чтобы использовать класс записей в любом случае, откройте базу данных и создайте объект набора записей, передав конструктору указатель на вашей `CDaoDatabase` объекта. Можно также создать `CDaoRecordset` объекта и позволить MFC создания временного пароля `CDaoDatabase` объект. Затем вызовите набора записей [откройте](#open) функция-член, показывающее, является ли объект recordset табличного типа, набор записей типа динамического или набора записей типа. Вызов `Open` выбирает данные из базы данных и извлекает первую запись.

Позволяет прокручивать записи и обработать их членов функции и данные члена объекта. Доступные операции зависят от того, является ли объект recordset табличного типа, набор записей типа динамического или набора записей типа и является ли он может обновляться или только для чтения — это зависит от возможностей базы данных или Open Database Connectivity (ODBC) источник данных. Для обновления записей, которые могут были изменены или добавлены с момента `Open` вызывать, вызвать для объекта [Requery](#requery) функция-член. Вызов объекта `Close` члена функции и уничтожьте объект, после завершения работы с его.

`CDaoRecordset` использует обмен полями записей DAO (DFX) для поддержки операций чтения и обновления полей записей через строго типизированные C++ членами вашей `CDaoRecordset` или `CDaoRecordset`-производного класса. Вы также можете реализовать динамическая привязка столбцов в базе данных без использования механизма DFX с помощью [GetFieldValue](#getfieldvalue) и [SetFieldValue](#setfieldvalue).

Дополнительные сведения см. в разделе «Объекта набора записей» справки DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="addnew"></a>  CDaoRecordset::AddNew

Вызывайте эту функцию элемента для добавления новой записи в набор записей, тип таблицы или динамического типа.

```
virtual void AddNew();
```

### <a name="remarks"></a>Примечания

Поля записи, первоначально равно Null. (В терминологии связанных баз данных, значение Null означает, что «предложений having нет значения» и не совпадает со значением NULL в C++). Чтобы завершить операцию, необходимо вызвать [обновления](#update) функция-член. `Update` Сохраняет изменения в источнике данных.

> [!CAUTION]
>  Если изменить запись, а затем перейти к другой записи без вызова `Update`, изменения будут утеряны без предупреждения.

При добавлении записи в наборе записей типа динамического путем вызова [AddNew](#addnew), записи, видимым в наборе записей и включены в базовой таблице, где он становится видимым для любой новый `CDaoRecordset` объектов.

Положение новой записи зависит от типа набора записей:

- В наборе записей, куда вставляется новая запись не гарантируется. Это поведение, изменить с помощью Microsoft Jet 3.0 по соображениям производительности и параллелизмом. Если ваша цель — сделать вновь добавленной записи текущей, получите закладки последней измененной записи и перемещения к закладке:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- В наборе записей табличный тип, для которого был указан индекс возвращаются записи вместо них соответствующие в порядке сортировки. Если индекс не был указан, новые записи возвращаются в конце набора записей.

Записи, которая была текущей до использования `AddNew` остаются актуальными. Если вы хотите сделать текущим новой записи и набор записей поддерживает закладки, вызов [SetBookmark](#setbookmark) закладку, определяется значение свойства LastModified базового объекта набора записей DAO. Это полезно для определения значения для счетчика (с автоматическим приращением) полей в записи добавлены. Дополнительные сведения см. в разделе [GetLastModifiedBookmark](#getlastmodifiedbookmark).

Если база данных поддерживает транзакции, можно сделать ваши `AddNew` вызовов, часть транзакции. Дополнительные сведения о транзакциях см. в разделе класса [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Обратите внимание, что следует вызывать [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) перед вызовом `AddNew`.

Недопустимо вызывать `AddNew` для объекта recordset, [откройте](#open) функция-член не был вызван. Объект `CDaoException` возникает исключение при вызове метода `AddNew` для объекта recordset, который не может быть добавлен. Можно определить, является ли набор записей может обновляться путем вызова [CanAppend](#canappend).

Метки framework изменить поля элементов данных, чтобы убедиться, что они записываются в запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Изменение значения поля обычно устанавливает для поля "грязных" автоматически, поэтому редко нужно вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться убедиться, что столбцы будут будут явно обновлены или вставлены независимо от какое значение является в элементе данных поля. Механизм DFX также использует механизм использования **ПСЕВДО NULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если не используется механизм двойную буферизацию, измените значение поля не задает автоматически поле как "грязную". В этом случае будет необходимо явным образом задать поле "грязный". Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.

> [!NOTE]
> Если есть записи, двойной буферизацией (то есть автоматическая поля включена проверка), вызов `CancelUpdate` восстановите переменные-члены в значения, они имели до `AddNew` или `Edit` был вызван.

Дополнительные сведения см в разделах «Метода AddNew», «Метод CancelUpdate», «Дата изменения свойства» и «Свойство EditMode» в справке DAO.

##  <a name="canappend"></a>  CDaoRecordset::CanAppend

Вызывайте эту функцию члена, чтобы определить, допускает ли ранее открывавшихся набора записей для добавления новых записей, вызвав [AddNew](#addnew) функция-член.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей разрешает добавление новых записей; в противном случае 0. `CanAppend` Возвращает 0, если вы открыли набора записей только для чтения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «Добавить метод» в справке DAO.

##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark

Вызывайте эту функцию члена, чтобы определить, допускает ли ранее открывавшихся набора записей необходимо отдельно пометить записей с помощью закладок.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей поддерживает закладки, в противном случае — 0.

### <a name="remarks"></a>Примечания

При использовании наборов записей, полностью основываясь таблиц ядра базы данных Microsoft Jet, можно использовать закладки за исключением на наборы записей типа, помечаются как прокрутки с последовательным. Другие продукты баз данных (внешних источников данных ODBC) могут не поддерживать закладки.

Дополнительные сведения см. в разделе «Свойство Bookmarkable» в справке DAO.

##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate

`CancelUpdate` Функция-член отменяет все ожидающие обновления из-за [изменить](#edit) или [AddNew](#addnew) операции.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Примечания

Например, если приложение вызывает `Edit` или `AddNew` функция-член и не вызван [обновление](#update), `CancelUpdate` отменяет все изменения, внесенные после `Edit` или `AddNew` был вызван.

> [!NOTE]
>  Если есть записи, двойной буферизацией (то есть автоматическая поля включена проверка), вызов `CancelUpdate` восстановите переменные-члены в значения, они имели до `AddNew` или `Edit` был вызван.

Если не `Edit` или `AddNew` операцию ожидания, `CancelUpdate` приводит к MFC для создания исключения. Вызовите [GetEditMode](#geteditmode) функция-член для определения того, если имеется отложенная операция, которую можно отменить.

Дополнительные сведения см. в разделе «Метод CancelUpdate» в справке DAO.

##  <a name="canrestart"></a>  CDaoRecordset::CanRestart

Вызывайте эту функцию члена, чтобы определить, допускает ли набор записей перезапуск его запроса (чтобы обновить свои записи), вызвав `Requery` функция-член.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `Requery` может вызываться для запуска набора записей запрос повторно, иначе — 0.

### <a name="remarks"></a>Примечания

Наборы записей типа таблицы не поддерживают `Requery`.

Если `Requery` — не поддерживается, вызовите [закрыть](#close) затем [откройте](#open) для обновления данных. Вы можете вызвать `Requery` обновление объекта набора записей основного запроса параметров после значения параметров были изменены.

Дополнительные сведения см. в разделе «Свойство перезапуска» в справке DAO.

##  <a name="canscroll"></a>  CDaoRecordset::CanScroll

Вызывайте эту функцию члена, чтобы определить, допускает ли прокрутка набора записей.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если можно прокручивать записи, иначе — 0.

### <a name="remarks"></a>Примечания

При вызове метода [откройте](#open) с `dbForwardOnly`, набор записей можно только прокрутку вперед.

Дополнительные сведения см. в разделе «Позиционирования текущей записи указатель с DAO» в справке DAO.

##  <a name="cantransact"></a>  CDaoRecordset::CanTransact

Вызывайте эту функцию члена, чтобы определить, допускает ли набор записей транзакций.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если базовый источник данных поддерживает транзакции, в противном случае — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «Транзакции свойство» в справке DAO.

##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate

Вызывайте эту функцию члена, чтобы определить, можно ли обновить набор записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если можно обновить набор записей (Добавление, обновление и удаление записей), иначе — 0.

### <a name="remarks"></a>Примечания

Набор записей могут быть доступны только для чтения, если базовый источник данных доступен только для чтения, или если вы указали `dbReadOnly` для *nOptions* при вызове [откройте](#open) для набора записей.

Дополнительные сведения см в разделах «Метода AddNew», «Изменить метод», «Метода Delete», «Метод обновления» и «Обновляемое свойство» в справке DAO.

##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset

Создает объект `CDaoRecordset`.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект или значение NULL. Если значение не NULL и `CDaoDatabase` объекта `Open` функция-член не был вызван для его подключения к источнику данных, пытается открыть его автоматически во время свой собственный набор записей [откройте](#open) вызова. Если передать значение NULL, `CDaoDatabase` объект создается и автоматически с помощью источника данных, вы указали, что если производного класса набора записей из подключенных `CDaoRecordset`.

### <a name="remarks"></a>Примечания

Вы можете использовать `CDaoRecordset` напрямую или являются производными класс конкретного приложения из `CDaoRecordset`. ClassWizard можно использовать для формирования классов набора записей.

> [!NOTE]
>  Если вы наследуете `CDaoRecordset` класса в производный класс должен предоставлять собственный конструктор. В конструкторе производного класса, вызовите конструктор `CDaoRecordset::CDaoRecordset`, передавая ему соответствующие параметры вместе.

Передать NULL в конструктор набора записей для `CDaoDatabase` объект создан и подключен для вас автоматически. Это удобно использовать, не требуется для создания и подключения `CDaoDatabase` объекта до создания набора записей. Если `CDaoDatabase` объекта не открыта, [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) также будет создан объект, использует рабочую область по умолчанию. Дополнительные сведения см. в разделе [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

##  <a name="close"></a>  CDaoRecordset::Close

Закрытие `CDaoRecordset` объект удаляется из коллекции открытые наборы записей в связанной базы данных.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Так как `Close` не уничтожает `CDaoRecordset` объекта, вы можете повторно использовать объект, вызвав `Open` на тот же источник данных или другого источника данных.

Все ожидающие [AddNew](#addnew) или [изменить](#edit) отменяются, и всех незавершенных транзакций выполняется откат. Если вы хотите сохранить отложенные добавления и изменения, вызвать [обновление](#update) перед вызовом метода `Close` для каждого набора записей.

Можно вызвать `Open` снова после вызова метода `Close`. Это позволяет повторно использовать объект recordset. Лучшим вариантом будет вызывать [Requery](#requery), если это возможно.

Дополнительные сведения см. в разделе «Метод Close» в справке DAO.

##  <a name="delete"></a>  CDaoRecordset::Delete

Вызовите эту функцию-член для удаления текущей записи в открытом объекте набора записей динамического или тип таблицы.

```
virtual void Delete();
```

### <a name="remarks"></a>Примечания

После успешного удаления, элементам данных полей присваивается значение Null, и необходимо явно вызвать один из функции-члены набора записей навигации ( [переместить](#move), [Seek](#seek), [ SetBookmark](#setbookmark), и т. д) чтобы отказаться от использования удаленной записи. При удалении записей из набора записей, необходимо выполнить текущей записи в наборе записей перед вызовом метода `Delete`; в противном случае MFC вызывает исключение.

`Delete` Удаляет текущую запись и делает ее недоступной. Несмотря на то, что нельзя изменить или использовать удаленной записи, остаются актуальными. После перемещения в другую запись, тем не менее нельзя вносить удаленной записи текущей еще раз.

> [!CAUTION]
>  Набор записей должно быть обновляемым и должен существовать допустимой записи текущего набора записей при вызове `Delete`. Например, если удалить запись, но не прокручиваются при перемещении к новой записи перед вызовом метода `Delete` , `Delete` вызывает [CDaoException](../../mfc/reference/cdaoexception-class.md).

Отменить удаление записи при использовании транзакций и вызове [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) функция-член. Если базовая таблица является таблицей первичного каскадом удалить связь, удаление текущей записи может также удалить одну или несколько записей во внешней таблице. Дополнительные сведения см. в разделе Определение «каскадное удаление» в справке DAO.

В отличие от `AddNew` и `Edit`, вызов `Delete` должен следовать вызов `Update`.

Дополнительные сведения см в разделах «Метода AddNew», «Изменить метод», «Метода Delete», «Метод обновления» и «Обновляемое свойство» в справке DAO.

##  <a name="dofieldexchange"></a>  CDaoRecordset::DoFieldExchange

Платформа вызывает эту функцию-член для автоматически обмена данными между элементами данных полей объекта набора записей и соответствующих столбцов текущей записи в источнике данных.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*PFX-файл*<br/>
Содержит указатель на `CDaoFieldExchange` объект. Платформа будет уже настроили этот объект для указать контекст операции обмена поля.

### <a name="remarks"></a>Примечания

Он также привязывает элементы данных параметра, если таковое имеется, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей. Exchange поля данных, называемый обмен полями записей DAO (DFX), работает в обоих направлениях: от объекта набора элементов данных полей сопоставляются с полями записей в источнике данных, а также из записи в источнике данных в объект набора записей. Если динамическая привязка столбцов не необходимо реализовать `DoFieldExchange`.

Единственным действием, обычно необходимо выполнить для реализации `DoFieldExchange` для набора записей производный класс является создание класса с помощью классов и укажите имена и типы данных элементов данных полей. Можно также добавить код, ClassWizard записывает для указания элементов данных параметров. Если все поля должны быть динамически связанной, эта функция будет выполняться неактивные, если вами параметризованные члены данных.

При объявлении класса производный набор записей с помощью классов, мастер создает переопределение `DoFieldExchange` , который похож на приведенный ниже:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>  CDaoRecordset::Edit

Вызовите эту функцию-член допускают изменения текущей записи.

```
virtual void Edit();
```

### <a name="remarks"></a>Примечания

При вызове метода `Edit` функция-член, изменения, внесенные в текущую запись полей копируемых в буфер копирования. После внесения необходимых изменений к записи, вызовите `Update` для сохранения изменений. `Edit` сохраняет значения членов данных набора записей. При вызове метода `Edit`, внесите изменения, затем вызвать `Edit` опять же, восстанавливаются значения записи он находился перед первым `Edit` вызова.

> [!CAUTION]
>  Если изменить запись, а затем выполнять любые операции, что перемещается в другой записи без предварительного вызова функции `Update`, изменения будут утеряны без предупреждения. Кроме того Если закрыть родительскую базу данных или набора записей, ваши измененной записи удаляются без предупреждения.

В некоторых случаях может потребоваться обновить столбец, делая Null (содержащий нет данных). Чтобы сделать это, вызовите `SetFieldNull` со значением параметра равным ИСТИНА – чтобы пометить поле значение Null; это также приводит к обновляемого столбца. Если необходимо добавить поле для записи к источнику данных, несмотря на то, что его значение не изменилось, вызовите `SetFieldDirty` со значением параметра равным TRUE. Это работает, даже если оно имело значение Null.

Метки framework изменить поля элементов данных, чтобы убедиться, что они записываются в запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Изменение значения поля обычно устанавливает для поля "грязных" автоматически, поэтому редко нужно вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться убедиться, что столбцы будут будут явно обновлены или вставлены независимо от какое значение является в элементе данных поля. Механизм DFX также использует механизм использования **ПСЕВДО NULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если не используется механизм двойную буферизацию, измените значение поля не задает автоматически поле как "грязную". В этом случае будет необходимо явным образом задать поле "грязный". Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.

Объект recordset, заблокированной pessimistically в многопользовательской среде, запись остается заблокированным с момента `Edit` используется до завершения обновления. Если набор записей оптимистически заблокирован, запись блокировки и по сравнению с предварительно измененной записи перед ее обновления в базе данных. Если запись была изменена с момента вызова `Edit`, `Update` сбоя операции и MFC вызывает исключение. Можно изменить режим блокировки с `SetLockingMode`.

> [!NOTE]
>  Для внешней базы данных форматов, таких как ODBC и устанавливаемый ISAM всегда используется оптимистическая блокировка.

Текущая запись остается текущее, после вызова метода `Edit`. Для вызова `Edit`, должно быть текущей записи. Если отсутствует текущая запись или набор записей не ссылается на таблицы открытого-типа или типа динамического объекта набора записей, возникает исключение. Вызов `Edit` вызывает `CDaoException` исключение при следующих условиях:

- Отсутствует текущая запись.

- Базы данных или набора записей доступен только для чтения.

- Поля в записи не являются обновляемыми.

- Базы данных или набора записей был открыт для монопольного использования другим пользователем.

- Другой пользователь заблокировал страницы, содержащей записи.

Если источник данных поддерживает транзакции, можно сделать `Edit` вызовов, часть транзакции. Обратите внимание, что следует вызывать `CDaoWorkspace::BeginTrans` перед вызовом `Edit` и после открытия набора записей. Также Обратите внимание, что при вызове `CDaoWorkspace::CommitTrans` он не может заменить за вызов метода `Update` для завершения `Edit` операции. Дополнительные сведения о транзакциях см. в разделе класса `CDaoWorkspace`.

Дополнительные сведения см в разделах «Метода AddNew», «Изменить метод», «Метода Delete», «Метод обновления» и «Обновляемое свойство» в справке DAO.

##  <a name="fillcache"></a>  CDaoRecordset::FillCache

Вызовите эту функцию-член для кэширования указанное число записей из набора записей.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Параметры

*pSize*<br/>
Указывает количество строк для заполнения в кэше. Если этот параметр не указан, значение определяется значение свойства CacheSize базового объекта DAO.

*pBookmark*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) указания закладки. Кэш заполняется, начиная с записи, обозначается данной закладки. Если этот параметр не указан, кэш будет заполнено, начиная с записи свойством CacheStart базового объекта DAO.

### <a name="remarks"></a>Примечания

Кэширование повышает производительность приложения, который извлекает или извлекает данные с удаленного сервера. Кэш — пространство в локальной памяти, которая содержит данные, наиболее недавно полученные от сервера на предположении, что данные будут, скорее всего, будет запрашиваться снова во время работы приложения. При запросе данных, базы данных Microsoft Jet сначала проверяет кэш для данных, а не получения их из на сервер, который занимает больше времени. С помощью кэширования данных на источники данных не ODBC не действует как данные не сохраняются в кэше.

А не ждать, пока кэш заполняется с записями, так как они не будут выбраны, вы можете явным образом заполнить кэш в любое время путем вызова `FillCache` функция-член. Это более быстрый способ заполнения кэша, так как `FillCache` извлекает несколько записей одновременно, вместо одной за раз. Например, во время отображения экранной каждой записи, что вызов приложения `FillCache` для выборки следующего один экран записей.

Любой базы данных ODBC для доступа к набору записей объектов может иметь локальный кэш. Чтобы создать кэш, откройте объект набора записей из удаленного источника данных и затем вызвать `SetCacheSize` и `SetCacheStart` функции-члены набора записей. Если *lSize* и *lBookmark* создать диапазон, частично или полностью за пределами диапазона, заданные `SetCacheSize` и `SetCacheStart`, часть набора записей за пределами этого диапазона, игнорируется и не является загружено в кэш. Если `FillCache` запросы записей больше, чем никак не на удаленный источник данных, будут выбраны только оставшихся записей, а исключение не создается.

Записей, выбранных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.

`FillCache` извлекает только те записи, которые еще не кэшируются. Чтобы выполнить принудительное обновление всех кэшированных данных, вызовите `SetCacheSize` функцию-член с *lSize* параметра равно 0, вызов `SetCacheSize` еще раз с *lSize* параметр равен размеру кэша первоначально запрошенную, а затем вызвать `FillCache`.

Дополнительные сведения см. в разделе «FillCache Method» в справке DAO.

##  <a name="find"></a>  CDaoRecordset::Find

Вызовите эту функцию-член для поиска определенной строки в наборе записей типа динамических подмножеств данных и моментальных снимков с помощью оператора сравнения.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lFindType*<br/>
Значение, указывающее тип требуемой операции поиска. Допустимые значения:

- AFX_DAO_NEXT местоположения следующего совпадения.

- AFX_DAO_PREV местоположения предыдущего совпадения.

- AFX_DAO_FIRST найти первое расположение соответствующую строку.

- AFX_DAO_LAST поиск последнего расположения соответствующую строку.

*lpszFilter*<br/>
Строковое выражение (например **ГДЕ** предложение в инструкцию SQL без слова **ГДЕ**) используется для поиска записи. Пример:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

Можно найти во-первых, следующего, предыдущего или последнего экземпляра строки. `Find` является виртуальная функция, поэтому можно переопределить его и добавить свою собственную реализацию. `FindFirst`, `FindLast`, `FindNext`, И `FindPrev` функции-члены вызывают `Find` функция-член, чтобы можно было использовать `Find` для управления поведением всех операций поиска.

Чтобы найти запись в наборе записей, тип таблицы, вызовите [Seek](#seek) функция-член.

> [!TIP]
>  Меньший набор записей, у вас есть, тем она эффективнее `Find` будет. В целом и особенно данных ODBC лучше создать новый запрос, который извлекает необходимые записи.

Дополнительные сведения см. в разделе «FindNext FindFirst, FindLast, FindPrevious методы» в справке DAO.

##  <a name="findfirst"></a>  CDaoRecordset::FindFirst

Вызов этой функции-члена для поиска первой записи, которая соответствует заданному условию.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строковое выражение (например **ГДЕ** предложение в инструкцию SQL без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

`FindFirst` Функция-член начинает поиск в начале набора записей и продолжается до конца набора.

Если вы хотите включить все записи из поиска (не только те, которые удовлетворяют определенному условию) использовать один из операции перемещения для перемещения по записям. Чтобы найти запись в наборе записей, тип таблицы, вызовите `Seek` функция-член.

Если запись, отвечающих условиям не найдено, указатель текущей записи не определен, и `FindFirst` возвращает ноль. Если набор записей содержит более одной записи, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи, не забудьте сохранить изменения, вызвав `Update` функция-член перед перемещением в другую запись. При перемещении на другую запись без обновления, изменения будут утеряны без предупреждения.

`Find` Поиск функций-членов из расположения и в направлении, указанным в следующей таблице:

|Операции по поиску|Begin|Направление поиска|
|---------------------|-----------|----------------------|
|`FindFirst`|Начало набора записей|Конец набора записей|
|`FindLast`|Конец набора записей|Начало набора записей|
|`FindNext`|Текущая запись|Конец набора записей|
|`FindPrevious`|Текущая запись|Начало набора записей|

> [!NOTE]
>  При вызове `FindLast`, базы данных Microsoft Jet полностью заполняет набор записей до начала поиска, если это уже не было сделано. Первый поиск может занять больше времени, чем последующих поисков.

С помощью одного из операции поиска не равносилен вызову метода `MoveFirst` или `MoveNext`, тем не менее, который просто делает первую или очередную запись текущей без указания условие. Вы можете выполнить операцию поиска с помощью операции перемещения.

При использовании операции поиска, имейте в виду следующее:

- Если `Find` возвращает ненулевое значение, не определен текущей записи. В этом случае следует выбрать положение указателя текущей записи к допустимой записи.

- Нельзя использовать операции поиска с помощью последовательного прокрутки тип моментального снимка набора записей.

- Следует использовать формат даты (месяц день год) США при поиске полей, содержащих даты, даже если не используется американская версия ядро базы данных Jet (Майкрософт); в противном случае подходящие записи могут быть не найдены.

- При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете обнаружить, что с помощью операции поиска работает медленно, особенно при работе с больших наборов записей. Можно повысить производительность с помощью SQL-запросов с помощью настройки **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или `CDaoQuerydef` объекты, которые извлекают записи определенного индексированных.

Дополнительные сведения см. в разделе «FindNext FindFirst, FindLast, FindPrevious методы» в справке DAO.

##  <a name="findlast"></a>  CDaoRecordset::FindLast

Вызывайте эту функцию члена, чтобы найти последнюю запись, которая соответствует заданному условию.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строковое выражение (например **ГДЕ** предложение в инструкцию SQL без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

`FindLast` Функция-член начинает поиск с конца набора данных и выполняет поиск назад к началу набора записей.

Если вы хотите включить все записи из поиска (не только те, которые удовлетворяют определенному условию) использовать один из операции перемещения для перемещения по записям. Чтобы найти запись в наборе записей, тип таблицы, вызовите `Seek` функция-член.

Если запись, отвечающих условиям не найдено, указатель текущей записи не определен, и `FindLast` возвращает ноль. Если набор записей содержит более одной записи, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение после первого вхождения и т. д.

> [!CAUTION]
>  При изменении текущей записи, убедитесь, что вы сохраните изменения, вызвав `Update` функция-член перед перемещением в другую запись. При перемещении на другую запись без обновления, изменения будут утеряны без предупреждения.

С помощью одного из операции поиска не равносилен вызову метода `MoveFirst` или `MoveNext`, тем не менее, который просто делает первую или очередную запись текущей без указания условие. Вы можете выполнить операцию поиска с помощью операции перемещения.

При использовании операции поиска, имейте в виду следующее:

- Если `Find` возвращает ненулевое значение, не определен текущей записи. В этом случае следует выбрать положение указателя текущей записи к допустимой записи.

- Нельзя использовать операции поиска с помощью последовательного прокрутки тип моментального снимка набора записей.

- Следует использовать формат даты (месяц день год) США при поиске полей, содержащих даты, даже если не используется американская версия ядро базы данных Jet (Майкрософт); в противном случае подходящие записи могут быть не найдены.

- При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете обнаружить, что с помощью операции поиска работает медленно, особенно при работе с больших наборов записей. Можно повысить производительность с помощью SQL-запросов с помощью настройки **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или `CDaoQuerydef` объекты, которые извлекают записи определенного индексированных.

Дополнительные сведения см. в разделе «FindNext FindFirst, FindLast, FindPrevious методы» в справке DAO.

##  <a name="findnext"></a>  CDaoRecordset::FindNext

Вызов этой функции-члена для следующей записи, который соответствует заданному условию поиска.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строковое выражение (например **ГДЕ** предложение в инструкцию SQL без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

`FindNext` Функция-член начинает поиск в текущей строке и выполняет поиск в конец набора записей.

Если вы хотите включить все записи из поиска (не только те, которые удовлетворяют определенному условию) использовать один из операции перемещения для перемещения по записям. Чтобы найти запись в наборе записей, тип таблицы, вызовите `Seek` функция-член.

Если запись, отвечающих условиям не найдено, указатель текущей записи не определен, и `FindNext` возвращает ноль. Если набор записей содержит более одной записи, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи, убедитесь, что вы сохраните изменения, вызвав `Update` функция-член перед перемещением в другую запись. При перемещении на другую запись без обновления, изменения будут утеряны без предупреждения.

С помощью одного из операции поиска не равносилен вызову метода `MoveFirst` или `MoveNext`, тем не менее, который просто делает первую или очередную запись текущей без указания условие. Вы можете выполнить операцию поиска с помощью операции перемещения.

При использовании операции поиска, имейте в виду следующее:

- Если `Find` возвращает ненулевое значение, не определен текущей записи. В этом случае следует выбрать положение указателя текущей записи к допустимой записи.

- Нельзя использовать операции поиска с помощью последовательного прокрутки тип моментального снимка набора записей.

- Следует использовать формат даты (месяц день год) США при поиске полей, содержащих даты, даже если не используется американская версия ядро базы данных Jet (Майкрософт); в противном случае подходящие записи могут быть не найдены.

- При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете обнаружить, что с помощью операции поиска работает медленно, особенно при работе с больших наборов записей. Можно повысить производительность с помощью SQL-запросов с помощью настройки **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или `CDaoQuerydef` объекты, которые извлекают записи определенного индексированных.

Дополнительные сведения см. в разделе «FindNext FindFirst, FindLast, FindPrevious методы» в справке DAO.

##  <a name="findprev"></a>  CDaoRecordset::FindPrev

Эта функция члена для поиска предыдущей записи, который соответствует заданному условию.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Параметры

*lpszFilter*<br/>
Строковое выражение (например **ГДЕ** предложение в инструкцию SQL без слова **ГДЕ**) используется для поиска записи.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

`FindPrev` Функция-член начинает поиск с текущей записи и ищет в обратном направлении к началу набора записей.

Если вы хотите включить все записи из поиска (не только те, которые удовлетворяют определенному условию) использовать один из операции перемещения для перемещения по записям. Чтобы найти запись в наборе записей, тип таблицы, вызовите `Seek` функция-член.

Если запись, отвечающих условиям не найдено, указатель текущей записи не определен, и `FindPrev` возвращает ноль. Если набор записей содержит более одной записи, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.

> [!CAUTION]
>  При изменении текущей записи, убедитесь, что вы сохраните изменения, вызвав `Update` функция-член перед перемещением в другую запись. При перемещении на другую запись без обновления, изменения будут утеряны без предупреждения.

С помощью одного из операции поиска не равносилен вызову метода `MoveFirst` или `MoveNext`, тем не менее, который просто делает первую или очередную запись текущей без указания условие. Вы можете выполнить операцию поиска с помощью операции перемещения.

При использовании операции поиска, имейте в виду следующее:

- Если `Find` возвращает ненулевое значение, не определен текущей записи. В этом случае следует выбрать положение указателя текущей записи к допустимой записи.

- Нельзя использовать операции поиска с помощью последовательного прокрутки тип моментального снимка набора записей.

- Следует использовать формат даты (месяц день год) США при поиске полей, содержащих даты, даже если не используется американская версия ядро базы данных Jet (Майкрософт); в противном случае подходящие записи могут быть не найдены.

- При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете обнаружить, что с помощью операции поиска работает медленно, особенно при работе с больших наборов записей. Можно повысить производительность с помощью SQL-запросов с помощью настройки **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или `CDaoQuerydef` объекты, которые извлекают записи определенного индексированных.

Дополнительные сведения см. в разделе «FindNext FindFirst, FindLast, FindPrevious методы» в справке DAO.

##  <a name="getabsoluteposition"></a>  CDaoRecordset::GetAbsolutePosition

Возвращает номер текущей записи в объект набора записей.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Возвращаемое значение

Целое число от 0 до число записей в наборе записей. Соответствует порядковый номер текущей записи в наборе записей.

### <a name="remarks"></a>Примечания

Примеры AbsolutePosition значение свойства базового объекта DAO (с нуля); значение 0 относится к первой записи в наборе записей. Можно определить количество заполненных записей в наборе, вызвав [GetRecordCount](#getrecordcount). Вызов `GetRecordCount` может занять некоторое время, так как он должен получить доступ к все записи, чтобы определить число.

Если существует по меньшей мере момент, когда нет записей в наборе записей; - 1 возвращается. Если текущая запись удаляется, примеры AbsolutePosition значение свойства не определен и MFC вызывает исключение, если такая ссылка. Для наборов записей добавляющий новые записи добавляются в конец последовательности.

> [!NOTE]
>  Это свойство не предназначено для использования в качестве символов-заместителей номер записи. Закладки по-прежнему рекомендованный способ сохранения и возврат к заданной позиции и являются единственным способом для размещения текущей записи для всех типов объектов набора записей. В частности определенной записи перемещается при удалении записи предшествует ей. Кроме того, нет никакой гарантий, что определенной записи будет же абсолютное положение, если набор записей будет повторно создан так, как порядок отдельных записей в наборе записей не гарантируется, если она создается с помощью инструкции SQL с помощью  **ORDERBY** предложение.

> [!NOTE]
>  Эта функция-член допустим только для динамического типа и наборами записей тип моментального снимка.

Дополнительные сведения см. в разделе «Свойство AbsolutePosition» в справке DAO.

##  <a name="getbookmark"></a>  CDaoRecordset::GetBookmark

Вызов этой функции-члена для получения значения закладки в определенной записи.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, представляющее закладку на текущей записи.

### <a name="remarks"></a>Примечания

При создании или открытии объекта набора записей, каждая из него записей уже с закладкой уникальный если их поддерживает. Вызовите `CanBookmark` чтобы определить, поддерживает ли набор записей закладки.

Можно сохранить закладку в текущей записи, следует назначить закладки, которую `COleVariant` объекта. Чтобы быстро вернуться к этой записи в любое время после перехода на другую запись, вызовите `SetBookmark` с параметром, соответствующий значению этого `COleVariant` объекта.

> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.

Дополнительные сведения см. в разделе «Закладка свойство» в справке DAO.

##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize

Вызывайте эту функцию члена, чтобы получить число записей в кэше.

```
long GetCacheSize();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, указывающее количество записей в наборе записей динамического типа, содержащий данные, локально кэшировать из источника данных ODBC.

### <a name="remarks"></a>Примечания

Кэширование данных повышает производительность приложения, получающий данные с удаленного сервера через объекты типа динамического набора записей. Кэш — это пространство в локальной памяти, которая содержит данные, наиболее недавно полученное от сервера, в случае, если данные будет запрошена во время работы приложения. При запросе данных, базы данных Microsoft Jet сначала проверяет кэш для запрошенных данных вместо того, чтобы их извлечения из на сервер, который занимает больше времени. Данные, которые получены из источника данных ODBC не сохраняется в кэше.

Любой источник данных ODBC, например подключенной таблицы, может иметь локальный кэш.

Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.

##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart

Вызывайте эту функцию члена, чтобы получить значение первой записи в наборе записей должен быть помещен в кэш.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `COleVariant` , указывающий закладки для первой записи в наборе записей должен быть помещен в кэш.

### <a name="remarks"></a>Примечания

Базы данных Microsoft Jet запрашивает записей в пределах диапазона кэша из кэша, и он запрашивает записи за пределами диапазона кэша с сервера.

> [!NOTE]
>  Записей, полученных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.

Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.

##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex

Вызовите для определения индекса в настоящий момент в индексированные таблицы типом эта функция-член `CDaoRecordset` объекта.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащая имя индекса в настоящий момент с набором записей табличный тип. Возвращает пустую строку, если индекс не было задано.

### <a name="remarks"></a>Примечания

Данный индекс является основой для упорядочения записей в наборе записей, тип таблицы и используется [Seek](#seek) функции-члена для поиска записей.

Объект `CDaoRecordset` объект может иметь более одного индекса, но можно использовать только один индекс одновременно (несмотря на то что [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) объект может иметь несколько индексов, определенным для него).

Дополнительные сведения см. раздел «Объект индекса», а также определение «текущий индекс» в справке DAO.

##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated

Вызовите эту функцию-член для извлечения дату и время создания базовой таблицы.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время создания базовой таблицы.

### <a name="remarks"></a>Примечания

Параметры даты и времени являются производными от компьютера, на котором был создан базовой таблицы.

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated

Вызовите эту функцию-член для извлечения дату и время последнего обновления схемы.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время последнего обновления структуры базовой таблицы (схема).

### <a name="remarks"></a>Примечания

Параметры даты и времени являются производными от последнее обновление структуры базовой таблицы (схемы) компьютера.

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName

Вызывайте эту функцию члена, чтобы определить имя базы данных для этого набора записей.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий путь и имя базы данных, от которого наследуется этот набор записей.

### <a name="remarks"></a>Примечания

Если набор записей создается без указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), а затем открыть базу данных по умолчанию, набор записей используется этот путь. По умолчанию эта функция возвращает пустую строку. Когда ClassWizard наследуется новый набор записей из `CDaoRecordset`, он создаст для вас эту функцию.

Следующий пример иллюстрирует использование двойная обратная косая черта (\\\\) в строке, как это и требуется для правильной интерпретации строки.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL

Для получения оператора SQL по умолчанию, на котором основан набор записей эта функция-член вызывается платформой.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий инструкцию SQL по умолчанию.

### <a name="remarks"></a>Примечания

Это может быть имя таблицы или SQL **ВЫБЕРИТЕ** инструкции.

Косвенно определите инструкцию SQL по умолчанию путем объявления класса набора записей с ClassWizard и ClassWizard выполняет эту задачу автоматически.

Если передается значение null, строка для [откройте](#open), а затем эта функция вызывается для определения имени таблицы или SQL для набора записей.

##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode

Вызовите эта функция-член для определения состояния редактирования, который является одним из следующих значений:

```
short GetEditMode();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указывающее состояние редактирования для текущей записи.

### <a name="remarks"></a>Примечания

|Значение|Описание|
|-----------|-----------------|
|`dbEditNone`|Ни одна из операций редактирования уже выполняется.|
|`dbEditInProgress`|`Edit` был вызван.|
|`dbEditAdd`|`AddNew` был вызван.|

Дополнительные сведения см. в разделе «Свойство EditMode» в справке DAO.

##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount

Вызовите эту функцию-член для получения числа полей (столбцов), определенных в наборе записей.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число полей в наборе записей.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.

##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo

Вызов этой функции-члена для получения сведений о полях в наборе записей.

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

*nIndex*<br/>
Отсчитываемый от нуля индекс предопределенные поля в коллекции полей набора записей, для поиска по индексу.

*FieldInfo*<br/>
Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения о наборе записей для извлечения. А также как они вызвать функцию возврата здесь перечислены доступные параметры. Для наилучшей производительности загрузки только уровня нужную информацию:

- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, тип, размер, атрибуты

- `AFX_DAO_SECONDARY_INFO` Сведения об основном, а также: порядковый номер позиции, необходимости разрешить нулевой длины, порядок сортировки, имя внешнего, исходное поле исходной таблицы

- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: текст проверки значение по умолчанию, правила проверки

*lpszName*<br/>
Имя поля.

### <a name="remarks"></a>Примечания

Одну версию функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.

Описание сведений, возвращаемых, см. в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведений на одном уровне, вы получите сведения о всех предыдущих уровней.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getfieldvalue"></a>  CDaoRecordset::GetFieldValue

Вызовите эту функцию-член для извлечения данных в набор записей.

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
Указатель на строку, которая содержит имя поля.

*varValue*<br/>
Ссылку на `COleVariant` объект, который будет хранить значение поля.

*nIndex*<br/>
Отсчитываемый от нуля индекс поля в коллекции полей набора записей, для поиска по индексу.

### <a name="return-value"></a>Возвращаемое значение

Две версии `GetFieldValue` , которые возвращают значение возвращаемого [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение поля.

### <a name="remarks"></a>Примечания

Поле можно искать по имени или по порядковому номеру.

> [!NOTE]
>  Более эффективно для вызова одной из версий эта функция-член, принимающий `COleVariant` ссылка на объект как параметр, а не вызывать версию, которая возвращает `COleVariant` объекта. Более поздние версии этой функции сохраняются для обеспечения обратной совместимости.

Используйте `GetFieldValue` и [SetFieldValue](#setfieldvalue) динамически привязывать поля во время выполнения, а не статически привязки столбцов с помощью [DoFieldExchange](#dofieldexchange) механизм.

`GetFieldValue` и `DoFieldExchange` механизм можно использовать для повышения производительности. Например, использовать `GetFieldValue` получить значение, которое требуется только по запросу и назначить этот вызов к кнопке «Дополнительные сведения» в интерфейсе.

Дополнительные сведения см в разделах «Объект поля» и «Значение свойства» в справке DAO.

##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount

Вызывайте эту функцию члена для определения количества индексов, доступных для объекта recordset табличный тип.

```
short GetIndexCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число индексов в наборе записей типа таблицы.

### <a name="remarks"></a>Примечания

`GetIndexCount` полезно для перебора всех индексов в наборе записей. Для этой цели используйте `GetIndexCount` в сочетании с [GetIndexInfo](#getindexinfo). Если эта функция-член вызывается на динамического или набора записей типа, MFC вызывает исключение.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo

Эта функция члена для получения различного рода сведения об индексе, определенные в базовой таблице набор записей.

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

*nIndex*<br/>
Отсчитываемый от нуля индекс в коллекции индексов таблицы, для поиска по числовой позиции.

*indexinfo*<br/>
Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения об индексе для извлечения. А также как они вызвать функцию возврата здесь перечислены доступные параметры. Для наилучшей производительности загрузки только уровня нужную информацию:

- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, сведения о поле, поля

- `AFX_DAO_SECONDARY_INFO` Сведения об основном, плюс: основной, Unique, Clustered, IgnoreNulls, необходимые, внешний

- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: числа различных объектов

*lpszName*<br/>
Указатель на имя объект индекса, для поиска по имени.

### <a name="remarks"></a>Примечания

Одну версию функции позволяет искать в индекс, по его позиции в коллекции. Другая версия позволяет искать индекса по имени.

Описание сведений, возвращаемых, см. в разделе [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведений на одном уровне, вы получите сведения о всех предыдущих уровней.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark

Вызовите эту функцию-член для получения наиболее недавно добавленные или измененные записи закладки.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `COleVariant` содержащий закладка, показывающая наиболее недавно добавленных или измененных записей.

### <a name="remarks"></a>Примечания

При создании или открытии объекта набора записей, каждая из него записей уже с закладкой уникальный если их поддерживает. Вызовите [GetBookmark](#getbookmark) чтобы определить, поддерживает ли набор записей закладки. Если набор записей не поддерживает закладки, `CDaoException` возникает исключение.

При добавлении записи, он отображается в конце набора записей и не является текущей записи. Чтобы сделать новую запись текущей, вызовите `GetLastModifiedBookmark` , а затем вызвать `SetBookmark` чтобы вернуться к вновь добавленной записи.

Дополнительные сведения см. в разделе «LastModified свойство» в справке DAO.

##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode

Вызов этой функции-члена для определения типа блокировки фактически для набора записей.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если тип блокировки пессимистическая, в противном случае 0 нежесткой блокировки.

### <a name="remarks"></a>Примечания

Пессимистической блокировки при по сути, на странице данных, содержащий запись, вы изменяете заблокирован, как только вы вызываете [изменить](#edit) функция-член. При вызове разблокируется страницы [обновление](#update) или [закрыть](#close) функция-член или любой из операций поиска или перемещения.

Если оптимистическая блокировка действует на странице данных, содержащий запись блокируется, только в том случае, пока запись обновляется с `Update` функция-член.

При работе с источниками данных ODBC, режим блокировки всегда является оптимистическим.

Дополнительные сведения см в разделах «LockEdits свойства» и «Блокировки поведение в многопользовательском приложений» в справке DAO.

##  <a name="getname"></a>  CDaoRecordset::GetName

Вызовите эту функцию-член для извлечения имени набора записей.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащая имя набора записей.

### <a name="remarks"></a>Примечания

Имя набора записей должно начинаться с буквы и может содержать не более 40 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.

Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue

Вызовите эту функцию-член для извлечения текущее значение указанного параметра, сохраненного в используемом объекте-DAOParameter.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Числовой позицию параметра в используемом объекте-DAOParameter.

*lpszName*<br/>
Имя параметра, значение которого требуется.

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение параметра.

### <a name="remarks"></a>Примечания

Параметр доступны по имени или по ее числовой позиции в коллекции.

Дополнительные сведения см. в разделе «Параметр объект» в справке DAO.

##  <a name="getpercentposition"></a>  CDaoRecordset::GetPercentPosition

При работе с динамического или набора записей типа, если вы вызываете `GetPercentPosition` до полного заполнения набора записей, объем перемещаемых задается относительно количество записей, доступных как указано, вызвав [GetRecordCount](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>Возвращаемое значение

Число от 0 до 100, указывающее Приблизительное расположение текущей записи в объекте набора записей, основанные на процентах записей в наборе записей.

### <a name="remarks"></a>Примечания

Вы можете перейти к последней записи путем вызова [MoveLast](#movelast) для завершения заполнения все наборы записей, но это может занять значительное время.

Вы можете вызвать `GetPercentPosition` на всех трех типов объектов набора записей, в том числе таблицы без индексов. Тем не менее, нельзя вызывать `GetPercentPosition` последовательного прокрутки моментальные снимки или набор записей, открываемые из сквозной запрос к внешней базе данных. Если отсутствует текущая запись, или текущей записи он был удален, `CDaoException` возникает исключение.

Дополнительные сведения см. в разделе «PercentPosition свойство» в справке DAO.

##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount

Вызывайте эту функцию члена, чтобы узнать, сколько записей в наборе записей были прочитаны.

```
long GetRecordCount();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей, доступных в объекте набора записей.

### <a name="remarks"></a>Примечания

`GetRecordCount` не позволяет определить, сколько записей содержащиеся в динамического или набора записей типа, пока все записи были прочитаны. Этого вызова функции-члена может занять значительное время.

После последней записи уже был осуществлен, возвращаемое значение указывает общее количество отмены удаления записей в наборе записей. Чтобы принудительно выполнить последнюю запись для доступа, вызовите `MoveLast` или `FindLast` функция-член для набора записей. Чтобы определить приблизительное количество записей, которые возвращает запрос также можно SQL Count.

Как приложение удаляет записи в наборе записей динамического типа, возвращаемое значение `GetRecordCount` уменьшается. Тем не менее, записи, удаленные другими пользователями, не отражаются по `GetRecordCount` до текущей записи находится в удаленной записи. Если выполнение транзакции, которая влияет на число записей, а впоследствии откатить транзакцию, `GetRecordCount` не будет отражать фактическое число оставшихся записей.

Значение `GetRecordCount` из набора записей типа не влияют изменения в базовых таблицах.

Значение `GetRecordCount` с типом таблицы набор записей отражает приблизительное количество записей в таблице и немедленно влияет как добавления и удаления записей в таблице.

Набор записей с записи не возвращает значение 0. При работе с таблицами или базами данных ODBC `GetRecordCount` всегда возвращается значение-1. Вызов `Requery` функции-члена для набора записей сбрасывает значение `GetRecordCount` просто так, будто запрос выполнен повторно.

Дополнительные сведения см. в разделе «RecordCount свойство» в справке DAO.

##  <a name="getsql"></a>  CDaoRecordset::GetSQL

Вызывайте эту функцию члена, чтобы получить инструкцию SQL, который использовался для выбора записей набора записей в том случае, когда он был открыт.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий инструкции SQL.

### <a name="remarks"></a>Примечания

Как правило, это будет SQL **ВЫБЕРИТЕ** инструкции.

Строка, возвращаемая `GetSQL` обычно отличается от любой строки, то может передать в набор записей в *lpszSQL* параметр [откройте](#open) функция-член. Это обусловлено записей создает полная инструкция SQL, в зависимости от того, что Вы передали `Open`, вы указали с помощью ClassWizard того, что указано в [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) данные-члены.

> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода `Open`.

Дополнительные сведения см. в разделе «Свойства SQL» в справке DAO.

##  <a name="gettype"></a>  CDaoRecordset::GetType

Эта функция-член вызывается после открытия набора записей, чтобы определить тип объекта набора записей.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений, указывающих тип набора записей:

- `dbOpenTable` Таблица тип набора записей

- `dbOpenDynaset` Копирование или изменение

- `dbOpenSnapshot` Набор записей типа

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.

##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule

Вызывайте эту функцию члена, чтобы определить правило, используемое для проверки данных.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` объект, содержащий значение, которое проверяет данные в записи, так как его изменить или добавить в таблицу.

### <a name="remarks"></a>Примечания

Это правило основана на тексте и применяется каждый раз, когда изменения базовой таблицы. Если данные не является допустимым, MFC вызывает исключение. Сообщения об ошибке — текст свертыванию объекта базового поля, если указан, или текст выражения, указанного в свойстве ValidationRule базового объекта поля. Можно вызвать [GetValidationText](#getvalidationtext) для получения текста сообщения об ошибке.

Например, в поле в запись, которая требует дня месяца может иметь правила проверки «BETWEEN день 1 до 31.»

Дополнительные сведения см. в разделе «Значение» в справке DAO.

##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText

Вызовите эту функцию-член для извлечения текста свертыванию базового объекта поля.

```
CString GetValidationText();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` объект, содержащий текст сообщения, которое отображается, если значение поля не удовлетворяет правило проверки базового объекта поля.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.

##  <a name="isbof"></a>  CDaoRecordset::IsBOF

Вызов этой функции-члена до перехода от записи к записи дополнительные ли вы вышли перед первой записи в наборе записей.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или прокручен назад до первой записи; в противном случае 0.

### <a name="remarks"></a>Примечания

Можно также вызвать `IsBOF` вместе с `IsEOF` определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода `Open`, если набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, имеющий по крайней мере одну запись, первая запись становится текущей записью и `IsBOF` возвращает 0.

Если первая запись становится текущей записью и вызывается `MovePrev`, `IsBOF` впоследствии будет возвращать ненулевое значение. Если `IsBOF` возвращает ненулевое значение, при вызове метода `MovePrev`, создается исключение. Если `IsBOF` возвращает ненулевое значение, текущей записи не определен и любое действие, которое требует текущей записи приводят к исключению.

Последствия определенным методам `IsBOF` и `IsEOF` параметры:

- Вызов `Open*` внутренне делает первую запись в наборе записей текущей записи путем вызова `MoveFirst`. Таким образом, вызов `Open` на пустой набор записей причины `IsBOF` и `IsEOF` возвращать ненулевое значение. (См. в следующей таблице поведение сбоя `MoveFirst` или `MoveLast` вызовите.)

- Все операции перемещения, найдите запись, успешно вызвать оба `IsBOF` и `IsEOF` возвращает значение 0.

- `AddNew` Вызова, за которым следует `Update` вызов, который успешно вставляет новую запись вызовет `IsBOF` для возврата 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` всегда останутся без изменений. Определенные ядром СУБД Microsoft Jet, указатель текущей записи пустому набору записей что в конце файла, поэтому любой новая запись вставляется после текущей записи.

- Любой `Delete` вызова, даже если он удаляет только оставшиеся записи из набора записей, не изменится значение `IsBOF` или `IsEOF`.

В этой таблице показано, какие операции перемещения разрешены с различными комбинациями `IsBOF` /  `IsEOF`.

||Примеры MoveFirst, MoveLast|MovePrev,<br /><br /> Переместить < 0|Переместить 0|MoveNext,<br /><br /> Переместить > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= не равно нулю,<br /><br /> `IsEOF`=0|Allowed|Исключение|Исключение|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`= не равно нулю|Allowed|Allowed|Исключение|Исключение|
|Оба ненулевое значение|Исключение|Исключение|Исключение|Исключение|
|Оба 0|Allowed|Allowed|Allowed|Allowed|

Позволяя операции перемещения не означает, что операция будет успешно находить записи. Просто указывает, что попытка выполнить указанную операцию перемещения может и не будет создавать исключение. Значение `IsBOF` и `IsEOF` функций-членов может измениться в результате попытки перехода.

Результат операции перемещения, которые не найдите запись, от значения `IsBOF` и `IsEOF` параметры показан в следующей таблице.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ненулевое значение|Ненулевое значение|
|`Move` 0|Без изменений|Без изменений|
|`MovePrev`, `Move` < 0|Ненулевое значение|Без изменений|
|`MoveNext`, `Move` > 0|Без изменений|Ненулевое значение|

Дополнительные сведения см. в разделе «BOF, EOF свойства» в справке DAO.

##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted

Вызывайте эту функцию члена, чтобы определить, был ли удален текущей записи.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей располагается на удаленную запись; в противном случае 0.

### <a name="remarks"></a>Примечания

Если вы прокрутите страницу к записи и `IsDeleted` возвращает значение TRUE (ненулевое), а затем необходимо перейти к другой записи, перед тем как выполнять другие операции, набор записей.

> [!NOTE]
>  Проверьте удаленные состояние для записи в наборе записей моментального снимка, или тип таблицы не требуется. Поскольку записей нельзя удалить из моментального снимка, нет необходимости вызывать `IsDeleted`. Для записей типа таблицы удаленные записи фактически удаляются из набора записей. После записи был удален, вам, другим пользователем или в другой набор записей, его нельзя прокрутить назад к этой записи. Таким образом, нет необходимости вызывать `IsDeleted`.

При удалении записи из подмножества, он удаляется из набора записей и его нельзя прокрутить назад к этой записи. Тем не менее, если запись в подмножества будет удалена другим пользователем или в другой набор записей на основе одной таблицы, `IsDeleted` возвратит TRUE при прокрутке позже с этой записью.

Дополнительные сведения см. в разделах «Метода Delete», «Дата изменения свойства» и «Свойство EditMode» в справке DAO.

##  <a name="iseof"></a>  CDaoRecordset::IsEOF

Вызовите эту функцию-член, при переходе от записи к записи дополнительные ли вы вышли за пределы последней записи в наборе записей.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или были прокручены за пределы последней записи; в противном случае 0.

### <a name="remarks"></a>Примечания

Можно также вызвать `IsEOF` определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода `Open`, если набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, имеющий по крайней мере одну запись, первая запись становится текущей записью и `IsEOF` возвращает 0.

Если последняя запись становится текущей записью, при вызове `MoveNext`, `IsEOF` впоследствии будет возвращать ненулевое значение. Если `IsEOF` возвращает ненулевое значение, при вызове метода `MoveNext`, создается исключение. Если `IsEOF` возвращает ненулевое значение, текущей записи не определен и любое действие, которое требует текущей записи приводят к исключению.

Последствия определенным методам `IsBOF` и `IsEOF` параметры:

- Вызов `Open` внутренне делает первую запись в наборе записей текущей записи путем вызова `MoveFirst`. Таким образом, вызов `Open` на пустой набор записей причины `IsBOF` и `IsEOF` возвращать ненулевое значение. (См. в следующей таблице поведение сбоя `MoveFirst` вызовите.)

- Все операции перемещения, найдите запись, успешно вызвать оба `IsBOF` и `IsEOF` возвращает значение 0.

- `AddNew` Вызова, за которым следует `Update` вызов, который успешно вставляет новую запись вызовет `IsBOF` для возврата 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` всегда останутся без изменений. Определенные ядром СУБД Microsoft Jet, указатель текущей записи пустому набору записей что в конце файла, поэтому любой новая запись вставляется после текущей записи.

- Любой `Delete` вызова, даже если он удаляет только оставшиеся записи из набора записей, не изменится значение `IsBOF` или `IsEOF`.

В этой таблице показано, какие операции перемещения разрешены с различными комбинациями `IsBOF` /  `IsEOF`.

||Примеры MoveFirst, MoveLast|MovePrev,<br /><br /> Переместить < 0|Переместить 0|MoveNext,<br /><br /> Переместить > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= не равно нулю,<br /><br /> `IsEOF`=0|Allowed|Исключение|Исключение|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`= не равно нулю|Allowed|Allowed|Исключение|Исключение|
|Оба ненулевое значение|Исключение|Исключение|Исключение|Исключение|
|Оба 0|Allowed|Allowed|Allowed|Allowed|

Позволяя операции перемещения не означает, что операция будет успешно находить записи. Просто указывает, что попытка выполнить указанную операцию перемещения может и не будет создавать исключение. Значение `IsBOF` и `IsEOF` функций-членов может измениться в результате попытки перехода.

Результат операции перемещения, которые не найдите запись, от значения `IsBOF` и `IsEOF` параметры показан в следующей таблице.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ненулевое значение|Ненулевое значение|
|`Move` 0|Без изменений|Без изменений|
|`MovePrev`, `Move` < 0|Ненулевое значение|Без изменений|
|`MoveNext`, `Move` > 0|Без изменений|Ненулевое значение|

Дополнительные сведения см. в разделе «BOF, EOF свойства» в справке DAO.

##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty

Вызовите эту функцию-член для определения ли указанное поле данными-членом подмножества помечен как «грязный» (изменить).

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которого требуется проверить, или значение NULL, чтобы определить потребность в любом из полей "грязных".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент данных заданного поля данных помечен как "грязный"; в противном случае 0.

### <a name="remarks"></a>Примечания

Данные в все измененными элементами данных полей должны быть переданы записи в источнике данных при обновлении текущей записи путем вызова `Update` функцию-член `CDaoRecordset` (вслед за вызовом `Edit` или `AddNew`). С этими сведениями, можно выполнить дополнительные действия, такие как Пометка элемента данных поля, чтобы пометить столбец, поэтому он не записываются в источник данных.

`IsFieldDirty` реализуется с помощью `DoFieldExchange`.

##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull

Вызывайте эту функцию члена, чтобы определить, помечен ли элемент данных указанного поля в наборе записей как Null.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которой вы хотите проверить, или значение NULL, чтобы определить, если поля имеют значение Null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент данных заданного поля помечается как Null. в противном случае 0.

### <a name="remarks"></a>Примечания

(В терминологии связанных баз данных, значение Null означает, что «предложений having нет значения» и не совпадает со значением NULL в C++). Если элемент данных поле помечается как Null, то он интерпретируется как столбец текущей записи, для которого не имеет смысла.

> [!NOTE]
>  В некоторых случаях с помощью `IsFieldNull` может оказаться неэффективным, как показано в следующем примере кода:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  Если вы используете динамическую привязку записей, не на основе `CDaoRecordset`, обязательно используйте VT_NULL, как показано в примере.

##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable

Вызовите эту функцию-член для определения ли элемент данных указанное поле значение «NULL» (может быть присвоено значение Null; C++ NULL не является таким же, как значение Null, что в терминологии связанных баз данных, означает, что «предложений having без значения»).

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которой вы хотите проверить, или значение NULL, чтобы определить, если поля имеют значение Null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент данных заданного поля может быть выполнено со значением Null; в противном случае 0.

### <a name="remarks"></a>Примечания

Поле, которое не может иметь значение Null должно иметь значение. При попытке такого поля задать значение NULL, при добавлении или обновлении записи источника данных отклоняет Добавление или обновление, и `Update` приведет к возникновению исключения. Исключение возникает при вызове `Update`, не в том случае, когда вы вызываете `SetFieldNull`.

##  <a name="isopen"></a>  CDaoRecordset::IsOpen

Вызывайте эту функцию члена, чтобы определить, открыт ли набор записей.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение объекте набора записей `Open` или `Requery` ранее был вызван функция-член и набор записей не закрыт; в противном случае 0.

### <a name="remarks"></a>Примечания

##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset::m_bCheckCacheForDirtyFields

Содержит флаг, указывающее, является ли кэшированные поля автоматически помечаются как "грязный" (измененные) и Null.

### <a name="remarks"></a>Примечания

Флаг по умолчанию используется значение TRUE. Этот параметр в этот элемент данных управляет весь механизм двойную буферизацию. Если пользователем задан флаг в значение TRUE, можно отключить кэширование на основе по полям, с помощью механизма DFX. Если пользователем задан флаг в значение FALSE, необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

Значение этого элемента данных, перед вызовом `Open`. Этот механизм используется главным образом для простоты использования. Производительность снижается из-за двойная буферизация полей при внесении изменений.

##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields

Содержит число элементов данных полей в классе наборов записей и количество столбцов, выбранных в набор записей из источника данных.

### <a name="remarks"></a>Примечания

Конструктор для класса набора записей необходимо инициализировать `m_nFields` с правильным количеством статически привязанных полей. ClassWizard записывает эту инициализацию для вас, можно использовать для объявления класса набора записей. Можно также написать его вручную.

Инфраструктура использует это число для управления взаимодействием между элементами данных полей и соответствующих столбцов текущей записи в источнике данных.

> [!NOTE]
>  Это число должно соответствовать количеству выходных столбцов, зарегистрированные в `DoFieldExchange` после вызова `SetFieldType` с параметром `CDaoFieldExchange::outputColumn`.

Вы можете привязать столбцы динамически с помощью параметра `CDaoRecordset::GetFieldValue` и `CDaoRecordset::SetFieldValue`. Если это сделать, то не следует выполнить приращение счетчика в `m_nFields` в соответствии с вызовов функции DFX вашей `DoFieldExchange` функция-член.

##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams

Содержит количество элементов данных параметров в классе записей — число параметров, переданных с запросом набора записей.

### <a name="remarks"></a>Примечания

Если набор записей класс элементов данных параметров, необходимо инициализировать конструктор для класса *m_nParams* с правильным числом. Значение *m_nParams* по умолчанию равно 0. При добавлении элементов данных параметров — это необходимо сделать вручную, необходимо также вручную добавить инициализацию в конструкторе класса в соответствии с числом параметров, указанных (который должен быть по крайней мере число '' заполнители в вашей *m_strFilter*  или *m_strSort* строка).

Платформа использует это число, когда он выполняет параметризацию запроса набора записей.

> [!NOTE]
>  Это число должно соответствовать количеству «params», зарегистрированный в `DoFieldExchange` после вызова `SetFieldType` с параметром `CFieldExchange::param`.

Дополнительные сведения см. в разделе «Параметр объект» в справке DAO.

##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset

Содержит указатель на интерфейс OLE для базового объекта набора записей DAO `CDaoRecordset` объекта.

### <a name="remarks"></a>Примечания

Используйте этот указатель, если требуется доступ к интерфейсу DAO напрямую.

Дополнительные сведения см. в разделе «Объекта набора записей» справки DAO.

##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase

Содержит указатель на `CDaoDatabase` объекта, через который набор записей подключен к источнику данных.

### <a name="remarks"></a>Примечания

Эта переменная задается двумя способами. Как правило, передать указатель на уже открытого `CDaoDatabase` объекта при создании объекта набора записей. Если передать значение NULL вместо этого `CDaoRecordset` создает `CDaoDatabase` объект и открывает его. В любом случае `CDaoRecordset` сохраняет указатель в этой переменной.

Обычно не требуется напрямую использовать указателем, сохраненным в `m_pDatabase`. При написании собственных расширений для `CDaoRecordset`, тем не менее, может потребоваться использовать указатель. Например, может потребоваться указатель Если вызывается собственные `CDaoException`(s).

Дополнительные сведения см. в разделе «Объект базы данных» в справке DAO.

##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter

Содержит строку, которая используется для создания **ГДЕ** предложения инструкции SQL.

### <a name="remarks"></a>Примечания

Он не включает зарезервированное слово **ГДЕ** для фильтрации набора записей. Использование этого элемента данных неприменим для записей типа таблицы. Использование `m_strFilter` не действует при открытии набора записей с помощью `CDaoQueryDef` указатель.

Используйте формат даты (месяц день год) США при фильтрации полей, содержащих даты, даже если не используется американская версия ядро базы данных Jet (Майкрософт); в противном случае данные можно отфильтровать не как ожидается.

Дополнительные сведения см. в разделе «Свойство фильтра» в справке DAO.

##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort

Содержит строку, содержащую **ORDERBY** предложения инструкции SQL без зарезервированных слов **ORDERBY**.

### <a name="remarks"></a>Примечания

Можно выполнить сортировку по динамического моментального снимка тип объекта набора записей.

Невозможно отсортировать объекты набора записей типа таблицы. Чтобы определить порядок сортировки recordset табличного типа, вызовите [SetCurrentIndex](#setcurrentindex).

Использование *m_strSort* не действует при открытии набора записей с помощью `CDaoQueryDef` указатель.

Дополнительные сведения см. в разделе «Сортировка свойство» в справке DAO.

##  <a name="move"></a>  CDaoRecordset::Move

Вызовите эту функцию-член для размещения записей *lRows* записей из текущей записи.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Параметры

*lRows*<br/>
Количество записей для перемещения вперед или назад. Положительные значения Переход вперед, в конец набора записей. Отрицательные значения перемещение назад, к началу.

### <a name="remarks"></a>Примечания

Можно переместить вперед или назад. `Move( 1 )` эквивалентно `MoveNext`, и `Move( -1 )` эквивалентен `MovePrev`.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Как правило, следует вызвать оба `IsBOF` и `IsEOF` перед операцией перемещения для определения, имеет ли набор записей какие-либо записи. После вызова метода `Open` или `Requery`, вызвать либо метод `IsBOF` или `IsEOF`.

> [!NOTE]
>  Если были прокручены за начало или конец набора записей ( `IsBOF` или `IsEOF` возвращает ненулевое значение), вызов `Move` вызывает `CDaoException`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

При вызове `Move` последовательного прокрутки моментального снимка, *lRows* параметр должен быть положительным целым числом и закладки не допускаются, поэтому вы можете переходить только.

Чтобы сделать первой, последней, следующей или предыдущей записи в наборе записей текущего вызова записей, `MoveFirst`, `MoveLast`, `MoveNext`, или `MovePrev` функция-член.

Дополнительные сведения см. в разделах «Переместить Method» и «Примеры MoveFirst, MoveLast, MoveNext и MovePrevious» в справке DAO.

##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst

Вызов этой функции-члена для первой записи в наборе записей (если таковые имеются) текущей записи.

```
void MoveFirst();
```

### <a name="remarks"></a>Примечания

Нет необходимости вызывать `MoveFirst` сразу после открытия набора записей. В это время первой записи (если таковые имеются) автоматически становится текущей записью.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Как правило, следует вызвать оба `IsBOF` и `IsEOF` перед операцией перемещения для определения, имеет ли набор записей какие-либо записи. После вызова метода `Open` или `Requery`, вызвать либо метод `IsBOF` или `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Используйте `Move` функции для перемещения между записями без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей типа, которые удовлетворяют определенному условию. Чтобы найти запись в объект набора записей таблицы type, вызовите `Seek`.

Если набор записей ссылается на набор записей таблицы type, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если вы не установите текущий индекс, не определен порядок возвращаемых записей.

При вызове метода `MoveLast` принудительно запрос в объекте recordset, на основе SQL-запроса или querydef, завершения и объект recordset заполняется полностью.

Нельзя вызывать `MoveFirst` или `MovePrev` функция-член с прокруткой только вперед моментального снимка.

Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «Переместить Method» и «Примеры MoveFirst, MoveLast, MoveNext и MovePrevious» в справке DAO.

##  <a name="movelast"></a>  CDaoRecordset::MoveLast

Эта функция члена вносить последней записи (если таковые имеются) в наборе записей текущей записи.

```
void MoveLast();
```

### <a name="remarks"></a>Примечания

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Как правило, следует вызвать оба `IsBOF` и `IsEOF` перед операцией перемещения для определения, имеет ли набор записей какие-либо записи. После вызова метода `Open` или `Requery`, вызвать либо метод `IsBOF` или `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Используйте `Move` функции для перемещения между записями без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей типа, которые удовлетворяют определенному условию. Чтобы найти запись в объект набора записей таблицы type, вызовите `Seek`.

Если набор записей ссылается на набор записей таблицы type, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если вы не установите текущий индекс, не определен порядок возвращаемых записей.

При вызове метода `MoveLast` принудительно запрос в объекте recordset, на основе SQL-запроса или querydef, завершения и объект recordset заполняется полностью.

Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «Переместить Method» и «Примеры MoveFirst, MoveLast, MoveNext и MovePrevious» в справке DAO.

##  <a name="movenext"></a>  CDaoRecordset::MoveNext

Вызывайте эту функцию члена, чтобы сделать следующей записи в наборе записей текущей записи.

```
void MoveNext();
```

### <a name="remarks"></a>Примечания

Рекомендуется вызывать `IsBOF` прежде чем пытаться перейти к предыдущей записи. Вызов `MovePrev` вызовет `CDaoException` Если `IsBOF` возвращает ненулевое значение, указывающее, что была выполнена прокрутка до первой записи, либо, записи не были выбраны, набор записей.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Как правило, следует вызвать оба `IsBOF` и `IsEOF` перед операцией перемещения для определения, имеет ли набор записей какие-либо записи. После вызова метода `Open` или `Requery`, вызвать либо метод `IsBOF` или `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Используйте `Move` функции для перемещения между записями без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей типа, которые удовлетворяют определенному условию. Чтобы найти запись в объект набора записей таблицы type, вызовите `Seek`.

Если набор записей ссылается на набор записей таблицы type, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если вы не установите текущий индекс, не определен порядок возвращаемых записей.

Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «Переместить Method» и «Примеры MoveFirst, MoveLast, MoveNext и MovePrevious» в справке DAO.

##  <a name="moveprev"></a>  CDaoRecordset::MovePrev

Вызывайте эту функцию члена, чтобы сделать предыдущей записи в текущую запись набора записей.

```
void MovePrev();
```

### <a name="remarks"></a>Примечания

Рекомендуется вызывать `IsBOF` прежде чем пытаться перейти к предыдущей записи. Вызов `MovePrev` вызовет `CDaoException` Если `IsBOF` возвращает ненулевое значение, указывающее, что была выполнена прокрутка до первой записи, либо, записи не были выбраны, набор записей.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Как правило, следует вызвать оба `IsBOF` и `IsEOF` перед операцией перемещения для определения, имеет ли набор записей какие-либо записи. После вызова метода `Open` или `Requery`, вызвать либо метод `IsBOF` или `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Используйте `Move` функции для перемещения между записями без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей типа, которые удовлетворяют определенному условию. Чтобы найти запись в объект набора записей таблицы type, вызовите `Seek`.

Если набор записей ссылается на набор записей таблицы type, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если вы не установите текущий индекс, не определен порядок возвращаемых записей.

Нельзя вызывать `MoveFirst` или `MovePrev` функция-член с прокруткой только вперед моментального снимка.

Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите `Move`.

Дополнительные сведения см. в разделах «Переместить Method» и «Примеры MoveFirst, MoveLast, MoveNext и MovePrevious» в справке DAO.

##  <a name="open"></a>  CDaoRecordset::Open

Необходимо вызвать эту функцию-член для извлечения записей для набора записей.

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

- `dbOpenDynaset` Набор записей типа динамического двунаправленный прокрутки. Это значение по умолчанию.

- `dbOpenTable` Набор записей табличный тип с двунаправленный прокрутки.

- `dbOpenSnapshot` Набор записей типа двунаправленный прокрутки.

*lpszSQL*<br/>
Указатель на строку, содержащую одно из следующих:

- Указатель NULL.

- Имя одного или нескольких tabledefs и/или querydefs (разделенных запятыми).

- SQL **ВЫБЕРИТЕ** инструкции (при необходимости с помощью SQL **ГДЕ** или **ORDERBY** предложение).

- Запрос к серверу.

*nOptions*<br/>
Один или несколько из перечисленных ниже параметров. Значение по умолчанию — 0. Ниже приведены возможные значения.

- `dbAppendOnly` Можно добавить только новые записи (только в наборе записей). Этот параметр буквально означает, что записи только на добавление. Классы баз данных MFC ODBC задать параметр только для добавления, который поддерживает записи для извлекаются и добавляются.

- `dbForwardOnly` Набор записей является снимком прокруткой только вперед.

- `dbSeeChanges` Создает исключение, если другой пользователь изменяет данные, которые вы изменяете.

- `dbDenyWrite` Другим пользователям нельзя изменить или добавить записи.

- `dbDenyRead` Другие пользователи не смогут просматривать записи (только для записей в тип таблицы).

- `dbReadOnly` Вы можете только просматривать записи; другие пользователи могут изменять их.

- `dbInconsistent` Несогласованные обновления разрешены (только в наборе записей).

- `dbConsistent` (Только для набора записей типа динамического) разрешены только согласованные обновления.

> [!NOTE]
>  Константы `dbConsistent` и `dbInconsistent` являются взаимоисключающими. Можно использовать один или другой, но не одновременно в заданном экземпляре `Open`.

*pTableDef*<br/>
Указатель на [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) объекта. Эта версия является допустимым только для записей типа таблицы. При использовании этого параметра `CDaoDatabase` указатель, используемый для создания `CDaoRecordset` не используется; вместо этого используется база данных, в котором находится tabledef.

*pQueryDef*<br/>
Указатель на [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) объекта. Эта версия является допустимым только для динамического типа и записей типа снимка. При использовании этого параметра `CDaoDatabase` указатель, используемый для создания `CDaoRecordset` не используется; вместо этого используется база данных, в котором находится querydef.

### <a name="remarks"></a>Примечания

Перед вызовом `Open`, необходимо создать объект recordset. Для этого можно использовать следующие способы.

- При создании объекта набора записей, передайте указатель на `CDaoDatabase` объект, который уже открыт.

- При создании объекта набора записей, передайте указатель на `CDaoDatabase` объект, не являющийся открытым. Открывает набор записей `CDaoDatabase` объекта, а не закроет его при закрытии объекта набора записей.

- При создании объекта набора записей, передайте указатель NULL. Набор записей объектов вызывает `GetDefaultDBName` для получения имени из Microsoft Access. Откройте файл MDB. Затем открывает набор записей `CDaoDatabase` объекта и сохраняет его открыть, до тех пор, пока открыт набор записей. При вызове `Close` для объекта recordset, `CDaoDatabase` объекта также закрывается.

    > [!NOTE]
    >  При открытии набора записей `CDaoDatabase` объекта, он открывает источник данных с помощью совмещаемый доступ.

Для версии `Open` , использующий *lpszSQL* параметр, после открытия набора записей можно получить записи в одном из следующих способов. Первый вариант — поместить функции DFX в вашей `DoFieldExchange`. Второй вариант — использовать динамической привязки путем вызова `GetFieldValue` функция-член. Эти параметры можно реализовать отдельно или в сочетании. Если они объединены, необходимо передать в инструкцию SQL самостоятельно при вызове `Open`.

При использовании второй версии `Open` здесь вы отправляете в `CDaoTableDef` объекта, полученные в результате столбцы будут доступны для привязки с помощью `DoFieldExchange` и DFX механизм и/или привязки динамически с помощью `GetFieldValue`.

> [!NOTE]
>  Можно вызывать только `Open` с помощью `CDaoTableDef` объект для записей типа таблицы.

При использовании третьей версии `Open` здесь вы отправляете в `CDaoQueryDef` объекта, что запрос будет выполняться, а полученные в результате столбцы будут доступны для привязки с помощью `DoFieldExchange` и DFX механизм и/или привязки динамически с помощью `GetFieldValue`.

> [!NOTE]
>  Можно вызывать только `Open` с помощью `CDaoQueryDef` объект для динамического типа и наборами записей тип моментального снимка.

Для первой версии `Open` , использующий `lpszSQL` параметр записи, выбранной на основе критериев, показано в следующей таблице.

|Значение параметра `lpszSQL`|Выбрано записей определяются|Пример|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Строка, возвращаемая `GetDefaultSQL`.||
|Разделенный запятыми список один или несколько tabledefs и/или querydef имена.|Все столбцы представлены в `DoFieldExchange`.|`"Customer"`|
|**ВЫБЕРИТЕ** список столбцов **FROM** список таблиц|Указанные столбцы из указанного tabledef(s) и/или querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Стандартные действия является передача значения NULL для `Open`; в этом случае `Open` вызовы `GetDefaultSQL`, переопределяемый член функции, ClassWizard приводит к возникновению ошибки при создании `CDaoRecordset`-производного класса. Это значение дает tabledef(s) и/или querydef имена, указанные в ClassWizard. Вместо этого можно указать другие сведения в *lpszSQL* параметра.

Все передаваемые `Open` создает окончательной строки SQL для запроса (строка может содержать SQL **ГДЕ** и **ORDERBY** добавляемой в конце предложения *lpszSQL* строки можно передать) и затем выполняет запрос. Сконструированная строка можно просмотреть путем вызова `GetSQL` после вызова метода `Open`.

Элементами данных полей класса набора записей привязанные к столбцам выбранных данных. Если возвращаются все записи, первая запись становится текущей записи.

Если вы хотите задать параметры для набора записей, таких как фильтр или сортировку, задайте `m_strSort` или `m_strFilter` после создания объекта набора записей, но перед вызовом метода `Open`. Если вы хотите обновить записи в наборе записей после набор записей уже открыт, вызовите `Requery`.

При вызове метода `Open` на динамического или набора записей типа, или если источник данных ссылается на инструкцию SQL или tabledef, который представляет подключенной таблицы, нельзя использовать `dbOpenTable` для аргумента типа; в противном случае MFC вызывает исключение. Чтобы определить, представляет ли объект tabledef подключенной таблицы, создайте [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) и вызовите его [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) функция-член.

Используйте `dbSeeChanges` флаг, если требуется перехватывать изменений, внесенных другим пользователем или в другую программу на вашем компьютере, при изменении или удалении той же записи. Например, если два пользователя начать редактирование ту же запись, первый пользователь, вызовите `Update` успешного выполнения функции-члена. Когда `Update` вызывается второй пользователь `CDaoException` возникает исключение. Аналогично Если второй пользователь пытается обратиться к `Delete` удалить запись и он уже был изменен первым пользователем, `CDaoException` происходит.

Как правило если пользователь получает это `CDaoException` при обновлении, код должен обновить содержимое полей и получить измененные значения. Если исключение возникает в процессе удаления, ваш код может отображать новые данные записей пользователю и сообщение о том, что данные были недавно изменены. На этом этапе ваш код мог запрашивать подтверждение, что пользователь по-прежнему хочет удалить запись.

> [!TIP]
>  Используйте параметр прокруткой только вперед (`dbForwardOnly`) для повышения производительности, когда приложение отправляет за один проход по набору записей, открытые из источника данных ODBC.

Дополнительные сведения см. в разделе «OpenRecordset Method» в справке DAO.

##  <a name="requery"></a>  CDaoRecordset::Requery

Вызовите эту функцию-член для перестроения (Обновить) набор записей.

```
virtual void Requery();
```

### <a name="remarks"></a>Примечания

Если возвращаются все записи, первая запись становится текущей записи.

В порядке для набора записей в соответствии с добавления и удаления, которые вы или другим пользователям больше всего к источнику данных, необходимо перестроить набор записей путем вызова `Requery`. Если набор записей является динамическим подмножеством данных, автоматически отражает обновлений, которые вы или другие пользователи его существующие записи (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать метод `Requery` для отражения изменений, с другими пользователями, а также добавления и удаления.

Для подмножества или моментального снимка вызовите `Requery` любое время, необходимо перестроить набор записей, используя значения параметров. Значение нового фильтра или сортировки, задав [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) перед вызовом `Requery`. Задайте новые параметры, задавая новые значения членов данных параметра перед вызовом `Requery`.

Если произошел сбой попытки повторного построения recordset, закрывается набор записей. Перед вызовом метода `Requery`, можно определить, является ли набор записей можно опросить путем вызова [CanRestart](#canrestart) функция-член. `CanRestart` не гарантирует, что `Requery` будет выполнена успешно.

> [!CAUTION]
>  Вызовите `Requery` только после вызова `Open`.

> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.

Нельзя вызывать `Requery` на динамического или набора записей типа, если вызывать `CanRestart` возвращает 0, или использовать его в набор записей типа таблицы.

Если оба `IsBOF` и `IsEOF` возвращать ненулевое значение, после вызова метода `Requery`, запрос не вернул какие-либо записи и набор записей будет не содержат данных.

Дополнительные сведения см. в разделе «Метод Requery», в справке DAO.

##  <a name="seek"></a>  CDaoRecordset::Seek

Вызовите эту функцию-член для обнаружения записи в объекте набора записей индексированные таблицы type, который удовлетворяет указанным критериям для текущего индекса и убедитесь, что запись текущей записи.

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

*lpszComparison*<br/>
Один из следующих строковых выражений: «< «,»\<=», «=», «> =», или «>».

*pKey1*<br/>
Указатель на [COleVariant](../../mfc/reference/colevariant-class.md) , значение которого соответствует первое поле в индексе. Обязательно.

*pKey2*<br/>
Указатель на `COleVariant` , значение которого соответствует второе поле в индексе, если таковые имеются. По умолчанию NULL.

*pKey3*<br/>
Указатель на `COleVariant` , значение которого соответствует третье поле в индексе, если таковые имеются. По умолчанию NULL.

*pKeyArray*<br/>
Указатель на массив типа Variant. Размер массива соответствует числу полей в индексе.

*nKeys*<br/>
Целое число, в зависимости от размера массива, то число полей в индексе.

> [!NOTE]
>  Не указывайте подстановочные знаки в ключах. Подстановочные знаки вызовет `Seek` для возврата без совпадающих записей.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Обнаружены совпадающие записи, в противном случае 0.

### <a name="remarks"></a>Примечания

Использовать второй версии (array) `Seek` обработка индексов четырех полей или больше.

`Seek` включает индекс высокой производительности, поиск записей типа таблицы. Необходимо задать текущий индекс, вызвав `SetCurrentIndex` перед вызовом `Seek`. Если задается индексом неуникальный ключевое поле или поля, `Seek` находит первой записи, которая не соответствует критериям. Если вы не установите индекса, создается исключение.

Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объекты должны быть объявлены явно ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  форма конструктора с *vtSrc* присвоено `VT_BSTRT` (ANSI) или с помощью `COleVariant` функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** с *vtSrc* присвоено `VT_BSTRT`.

При вызове `Seek`, вы передаете один или несколько значений ключа, а оператор сравнения ("< «,»\<=», «=», «> =», или «>»). `Seek` выполняет поиск по указанным ключевых полей и находит первой записи, которая удовлетворяет критериям, заданным *lpszComparison* и *pKey1*. После нахождения `Seek` возвращает ненулевое значение и делает текущей записи. Если `Seek` не может найти совпадения, `Seek` возвращает ноль, а не определено текущей записи. При использовании DAO напрямую, необходимо явно проверить свойство NoMatch.

Если `lpszComparison` «=», «> =», или «>», `Seek` начинается с индекса. Если *lpszComparison* является «<» или «< =», `Seek` начинается по окончании индекса и ищет в обратном направлении, если существуют дублирующиеся индекс записи в конце. В этом случае `Seek` начинается с произвольной запись среди повторяющихся указателя в конце индекса.

Существует не быть текущей записи при использовании `Seek`.

Чтобы найти запись типа динамического или набора записей типа, удовлетворяющего определенному условию, используйте операции поиска. Чтобы включить все записи, не только те, которые удовлетворяют определенному условию, используйте операции перемещения для перемещения по записям.

Нельзя вызывать `Seek` на подключенной таблицы любого типа, так как вложенные таблицы должен быть открыт как динамического или набора записей типа. Тем не менее при вызове метода `CDaoDatabase::Open` непосредственно открыть базу данных ISAM устанавливаемые, можно последовательно вызвать методы `Seek` в таблицах в этой базе данных, несмотря на то, что производительность может быть медленно.

Дополнительные сведения см. в разделе «Поиск Method» в справке DAO.

##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition

Задает относительный номер текущей записи в объект набора записей.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Параметры

*lPosition*<br/>
Соответствует порядковый номер текущей записи в наборе записей.

### <a name="remarks"></a>Примечания

Вызов `SetAbsolutePosition` позволяет разместить на указатель текущей записи к конкретной записи, в зависимости от его порядковый номер типа динамического или набора записей типа. Вы также можете определить номер текущей записи, вызвав [GetAbsolutePosition](#getabsoluteposition).

> [!NOTE]
>  Эта функция-член допустим только для динамического типа и наборами записей тип моментального снимка.

Примеры AbsolutePosition значение свойства базового объекта DAO (с нуля); значение 0 относится к первой записи в наборе записей. Установка значения, большего, чем причин заполненный записей MFC для создания исключения. Можно определить количество заполненных записей в наборе, вызвав `GetRecordCount` функция-член.

Если текущая запись удаляется, примеры AbsolutePosition значение свойства не определен и MFC вызывает исключение, если такая ссылка. Новые записи добавляются в конец последовательности.

> [!NOTE]
>  Это свойство не предназначено для использования в качестве символов-заместителей номер записи. Закладки по-прежнему рекомендуемый способ сохранения и возврат к заданной позиции и являются единственным способом для размещения текущей записи для всех типов объектов набора записей, которые поддерживают закладки. В частности определенной записи перемещается при удалении записи предшествует ей. Кроме того, нет никакой гарантий, что определенной записи будет же абсолютное положение, если набор записей будет повторно создан так, как порядок отдельных записей в наборе записей не гарантируется, если она создается с помощью инструкции SQL с помощью  **ORDERBY** предложение.

Дополнительные сведения см. в разделе «Свойство AbsolutePosition» в справке DAO.

##  <a name="setbookmark"></a>  CDaoRecordset::SetBookmark

Вызовите эту функцию-член для позиционирования в набор записей на запись, содержащую указанную закладку.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение для определенной записи.

### <a name="remarks"></a>Примечания

При создании или открытии объекта набора записей, каждый записи уже имеет уникальный закладки. Закладка для текущей записи можно получить, вызвав `GetBookmark` и сохранение его на `COleVariant` объекта. Возможность позже вернуться к этой записи путем вызова `SetBookmark` с использованием значения сохраненную закладку.

> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.

Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объект должен быть объявлен явным образом ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  форма конструктора с *vtSrc* присвоено `VT_BSTRT` (ANSI) или с помощью `COleVariant` функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** с *vtSrc* присвоено `VT_BSTRT`.

Дополнительные сведения см. в разделах «Закладка свойства» и Bookmarkable свойство» в справке DAO.

##  <a name="setcachesize"></a>  CDaoRecordset::SetCacheSize

Вызывайте эту функцию член, чтобы задать число записей должен быть помещен в кэш.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Параметры

*lSize*<br/>
Указывает количество записей. Стандартное значение — 100. Значение 0 отключает кэширование. Параметр должна составлять от 5 до 1200 записей. Кэш может использовать значительное количество памяти.

### <a name="remarks"></a>Примечания

Кэш — это пространство в локальной памяти, которая содержит данные, наиболее недавно полученное от сервера, в случае, если данные будет запрошена во время работы приложения. Кэширование данных повышает производительность приложения, получающий данные с удаленного сервера через объекты типа динамического набора записей. При запросе данных, базы данных Microsoft Jet сначала проверяет кэш для запрошенных данных вместо того, чтобы их извлечения из на сервер, который занимает больше времени. Данные, которые получены из источника данных ODBC не сохраняется в кэше.

Любой источник данных ODBC, например подключенной таблицы, может иметь локальный кэш. Чтобы создать кэш, откройте объект набора записей из удаленного источника данных, вызов `SetCacheSize` и `SetCacheStart` функции-члены, а затем вызовите `FillCache` функция-член или шаг по записям с помощью одного из операции перемещения. *LSize* параметр `SetCacheSize` функция-член может основываться на количество записей, приложение может работать с за один раз. Например, если набор записей используется как источник данных для отображения на экране, можно передать `SetCacheSize` *lSize* параметра в виде 20 для отображения 20 записей за один раз.

Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.

##  <a name="setcachestart"></a>  CDaoRecordset::SetCacheStart

Вызов этой функции-члена для указания закладки для первой записи в наборе записей должен быть помещен в кэш.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Объект [COleVariant](../../mfc/reference/colevariant-class.md) , указывающий закладки для первой записи в наборе записей должен быть помещен в кэш.

### <a name="remarks"></a>Примечания

Можно использовать значение любой записи для *varBookmark* параметр `SetCacheStart` функция-член. Сделать нужно начать с текущей записи кэша, установить закладку для этой записи с помощью [SetBookmark](#setbookmark)и передать значение параметра для `SetCacheStart` функция-член.

Базы данных Microsoft Jet запрашивает записей в пределах диапазона кэша из кэша, и он запрашивает записи за пределами диапазона кэша с сервера.

Записей, полученных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.

Для принудительного обновления всех кэшированных данных, передать *lSize* параметр `SetCacheSize` как 0, вызов `SetCacheSize` снова с размером кэша вы запрашивали, а затем вызовите `FillCache` функция-член.

Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объект должен быть объявлен явным образом ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  форма конструктора с *vtSrc* присвоено `VT_BSTRT` (ANSI) или с помощью `COleVariant` функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** с *vtSrc* присвоено `VT_BSTRT`.

Дополнительные сведения см. в разделе CacheSize, CacheStart свойства» в справке DAO.

##  <a name="setcurrentindex"></a>  CDaoRecordset::SetCurrentIndex

Эта функция члена следует установить индекс на набор записей типа таблицы.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Параметры

*lpszIndex*<br/>
Указатель, содержащая имя индекса, чтобы задать.

### <a name="remarks"></a>Примечания

Записи в базовых таблицах не хранятся в определенном порядке. Индекс параметра изменяет порядок записей, возвращаемых из базы данных, но он не влияет на порядок, в котором хранятся записи. Указанный индекс должен быть уже определена. Если попытаться использовать объект индекса, который не существует, или индекс не задан, при вызове [Seek](#seek), MFC вызывает исключение.

Новый индекс для таблицы можно создать путем вызова [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) и Добавление нового индекса в коллекцию индексов базовой tabledef путем вызова [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), и затем повторно открыть набор записей.

Записей, возвращаемых из набора записей типа таблицы может упорядочиваться только индексы, определенные для базовых tabledef. Чтобы отсортировать записи в ином порядке, можно открыть динамического или набора записей типа, используя SQL **ORDERBY** предложении хранятся в [CDaoRecordset::m_strSort](#m_strsort).

Дополнительные сведения см. раздел «Объект индекса», а также определение «текущий индекс» в справке DAO.

##  <a name="setfielddirty"></a>  CDaoRecordset::SetFieldDirty

Вызовите эту функцию-член для пометки элемента данных поля в наборе записей, как измененные или как без изменений.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, помечаются все поля элементов данных в наборе записей. (C++ NULL не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having без значения.»)

*bDirty*<br/>
Значение TRUE, если элемент данных полю будет помечен как «грязный» (измененные). В противном случае значение FALSE, если элемент данных полю будет помечен как «чистые» (без изменений).

### <a name="remarks"></a>Примечания

Пометка полей как неизмененные гарантирует, что поле не обновляется.

Метки framework изменить поля элементов данных, чтобы убедиться, что они записываются в запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Изменение значения поля обычно устанавливает для поля "грязных" автоматически, поэтому редко нужно вызывать `SetFieldDirty` самостоятельно, но иногда может потребоваться убедиться, что столбцы будут будут явно обновлены или вставлены независимо от того, какое значение в поле данных член. Механизм DFX также использует механизм использования PSEUDONULL. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Если не используется механизм двойную буферизацию, измените значение поля не задает автоматически поле как "грязную". В этом случае будет необходимо явным образом задать поле как "грязную". Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.

> [!NOTE]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).

Использование значения NULL для первого аргумента функции, будет применяться ко всем функция `outputColumn` поля, не **param** поля в `CDaoFieldExchange`. Например вызов

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

будет только при задании `outputColumn` поля NULL; **param** поля не будут затронуты.

Для работы на **param**, необходимо указать фактический адрес лица, **param** требуется для работы, такие как:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Это означает, что нельзя задать все **param** поля значение NULL, как и с помощью `outputColumn` поля.

`SetFieldDirty` реализуется с помощью `DoFieldExchange`.

##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull

Вызовите эту функцию-член для пометки элемента данных поля в наборе записей, как Null (в частности, имеющая значение не) или как отличное от Null.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, помечаются все поля элементов данных в наборе записей. (C++ NULL не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having без значения.»)

*bNull*<br/>
Ненулевое значение, если элемент данных поля помечаются как имеющие нет значения (Null). В противном случае — 0, если элемент данных поля будет помечен как отличное от Null.

### <a name="remarks"></a>Примечания

`SetFieldNull` используется для полей, привязанных к `DoFieldExchange` механизм.

При добавлении новой записи в набор записей, все поля элементов данных изначально присвоено значение Null и помечен как «грязный» (измененные). При извлечении записи из источника данных, ее столбцы уже имеют значения либо равны Null. Если это неприемлемо сделать поле значение Null, [CDaoException](../../mfc/reference/cdaoexception-class.md) возникает исключение.

При использовании механизма двойную буферизацию, к примеру, если требуется специально назначения поля текущей записи как не имеющий значение, вызов `SetFieldNull` с *bNull* присвоено значение TRUE, чтобы пометить его как Null. Если ранее был помечен поле значение Null, а теперь нужно ему присваивается значение, просто задайте его новое значение. Необходимо удалить флаг Null с помощью `SetFieldNull`. Чтобы определить, разрешено ли поле иметь значение Null, вызовите [IsFieldNullable](#isfieldnullable).

Если вы не используете механизм двойную буферизацию, измените значение поля не задает автоматически поле как "грязный" и отличных от Null. В частности, необходимо установить поля "грязных" и отличных от Null. Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.

Механизм DFX использует использование PSEUDONULL. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).

Использование значения NULL, первый аргумент функции будет применяться только к функции `outputColumn` поля, не **param** поля в `CDaoFieldExchange`. Например вызов

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

будет только при задании `outputColumn` поля NULL; **param** поля не будут затронуты.

##  <a name="setfieldvalue"></a>  CDaoRecordset::SetFieldValue

Вызывайте эту функцию член значение поля, либо по порядковому номеру, либо путем изменения значения строки.

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
Ссылку на [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение поля.

*nIndex*<br/>
Целое число, представляющее порядковый номер поля в коллекции полей набора записей (от нуля).

*lpszValue*<br/>
Указатель на строку, содержащую значение поля.

### <a name="remarks"></a>Примечания

Используйте `SetFieldValue` и [GetFieldValue](#getfieldvalue) динамически привязывать поля во время выполнения, а не статически привязки столбцов с помощью [DoFieldExchange](#dofieldexchange) механизм.

Обратите внимание, что если вы не создаете набор Юникод, необходимо использовать разновидность `SetFieldValue` , не содержащий `COleVariant` параметра, или `COleVariant` объект должен быть объявлен явным образом ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  форма конструктора с *vtSrc* присвоено `VT_BSTRT` (ANSI) или с помощью `COleVariant` функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** с *vtSrc* присвоено `VT_BSTRT`.

Дополнительные сведения см в разделах «Объект поля» и «Значение свойства» в справке DAO.

##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull

Вызывайте эту функцию элемента требуется задать поле значение Null.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс поля в наборе записей, для поиска по индексу (с нуля).

*lpszName*<br/>
Имя поля в наборе записей, для поиска по имени.

### <a name="remarks"></a>Примечания

C++ NULL не является таким же, как значение Null, что в терминологии связанных баз данных, означает, что «необходимости нет значения».

Дополнительные сведения см в разделах «Объект поля» и «Значение свойства» в справке DAO.

##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode

Вызывайте эту функцию члена, чтобы задать тип блокировки для набора записей.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Параметры

*bPessimistic*<br/>
Флаг, указывающий тип блокировки.

### <a name="remarks"></a>Примечания

Когда пессимистической блокировки действует, содержащий запись, вы изменяете страниц блокировки сразу после вызова `Edit` функция-член. При вызове разблокируется страницы `Update` или `Close` функция-член или любой из операций поиска или перемещения.

Если оптимистическая блокировка действует, содержащий запись страниц блокируется, только в том случае, пока запись обновляется с `Update` функция-член.

Если страница заблокирован, ни один другой пользователь можно изменить записей на одной странице. При вызове метода `SetLockingMode` и передать ненулевое значение и другой пользователь уже заблокирован страницы, возникает исключение при вызове `Edit`. Другие пользователи могут считывать данные из блокировки страниц.

При вызове метода `SetLockingMode` нуль и более поздних версий вызовите `Update` странице заблокировано другим пользователем, возникает исключение. Чтобы увидеть изменения, внесенные в запись другим пользователем (и отменить изменения), вызовите `SetBookmark` функцию-член с значение текущей записи.

При работе с источниками данных ODBC, режим блокировки всегда является оптимистическим.

##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue

Вызывайте эту функцию член, чтобы задать значение параметра в наборе записей во время выполнения.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);


virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Числовой позицию параметра в коллекции параметров querydef.

*var*<br/>
Задаваемое значение; см. в разделе "Примечания".

*lpszName*<br/>
Имя параметра, значение которого требуется задать.

### <a name="remarks"></a>Примечания

Параметр должна быть уже установлена как часть строки SQL набора записей. Параметр доступны по имени или по позиции индекса в коллекции.

Укажите значение, устанавливаемое как `COleVariant` объекта. Дополнительные сведения о настройке в нужное значение и введите ваш `COleVariant` объекта, см. в разделе класса [COleVariant](../../mfc/reference/colevariant-class.md). Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объект должен быть объявлен явным образом ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  форма конструктора с *vtSrc* присвоено `VT_BSTRT` (ANSI) или с помощью `COleVariant` функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** с *vtSrc* присвоено `VT_BSTRT`.

##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull

Вызовите эта функция-член для параметра значение Null.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс поля в наборе записей, для поиска по индексу (с нуля).

*lpszName*<br/>
Имя поля в наборе записей, для поиска по имени.

### <a name="remarks"></a>Примечания

C++ NULL не является таким же, как значение Null, что в терминологии связанных баз данных, означает, что «необходимости нет значения».

##  <a name="setpercentposition"></a>  CDaoRecordset::SetPercentPosition

Вызывайте эту функцию члена, чтобы задать значение, изменяющее Приблизительное расположение текущей записи в объекте набора записей, основанные на процентах записей в наборе записей.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Параметры

*fPosition*<br/>
Число от 0 до 100.

### <a name="remarks"></a>Примечания

При работе с динамического или набора записей типа моментального снимка, сначала нужно заполнить набор записей путем перемещения к последней записи, перед вызовом метода `SetPercentPosition`. При вызове метода `SetPercentPosition` до полного заполнения набора записей, объем перемещаемых задается относительно количество записей, доступных как указано по значению [GetRecordCount](#getrecordcount). Вы можете перейти к последней записи путем вызова `MoveLast`.

При вызове метода `SetPercentPosition`, становится текущей записи по приблизительное позиции, соответствующего этому значению.

> [!NOTE]
>  Вызов `SetPercentPosition` для перемещения текущей записи к конкретной записи в наборе записей не рекомендуется. Вызовите [SetBookmark](#setbookmark) вместо этого функция-член.

Дополнительные сведения см. в разделе «PercentPosition свойство» в справке DAO.

##  <a name="update"></a>  CDaoRecordset::Update

Это функция-член вызывается после вызова `AddNew` или `Edit` функция-член.

```
virtual void Update();
```

### <a name="remarks"></a>Примечания

Этот вызов необходим для завершения `AddNew` или `Edit` операции.

Оба `AddNew` и `Edit` Подготовка буфера редактирования, в котором размещается добавленных или измененных данных для сохранения в источнике данных. `Update` сохраняет данные. Обновляются только поля, помеченные или обнаружено как измененный.

Если источник данных поддерживает транзакции, можно сделать `Update` вызова (и его соответствующее `AddNew` или `Edit` вызовите) частью транзакции.

> [!CAUTION]
> При вызове метода `Update` без предварительного вызова либо `AddNew` или `Edit`, `Update` вызывает `CDaoException`. При вызове метода `AddNew` или `Edit`, необходимо вызвать `Update` перед вызовом метода [MoveNext](#movenext) или закрыть соединение с источником данных или набора записей. В противном случае изменения будут утеряны без уведомления.

Объект recordset, заблокированной pessimistically в многопользовательской среде, запись остается заблокированным с момента `Edit` используется до завершения обновления. Если набор записей оптимистически заблокирован, запись блокировки и по сравнению с предварительно измененной записи перед ее обновления в базе данных. Если запись была изменена с момента вызова `Edit`, `Update` сбоя операции и MFC вызывает исключение. Можно изменить режим блокировки с `SetLockingMode`.

> [!NOTE]
> Для внешней базы данных форматов, таких как ODBC и устанавливаемый ISAM всегда используется оптимистическая блокировка.

Дополнительные сведения см в разделах «Метода AddNew», «Метод CancelUpdate», «Метода Delete», «LastModified Property», «Метод обновления» и «Свойство EditMode» в справке DAO.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)<br/>
