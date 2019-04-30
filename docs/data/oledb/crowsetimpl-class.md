---
title: Класс CRowsetImpl
ms.date: 11/04/2016
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
- CRowsetImpl::m_strCommandText
- CRowsetImpl.m_strCommandText
- CRowsetImpl::m_strIndexText
- CRowsetImpl.m_strIndexText
helpviewer_keywords:
- CRowsetImpl class
- NameFromDBID method
- SetCommandText method
- GetColumnInfo method
- GetCommandFromID method
- ValidateCommandID method
- m_rgRowData
- m_strCommandText
- m_strIndexText
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
ms.openlocfilehash: 1fac3a74ca259fe3b680355fadc7f9bbd6e3cc13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368712"
---
# <a name="crowsetimpl-class"></a>Класс CRowsetImpl

Предоставляет стандартную реализацию набора строк OLE DB без необходимости множественное наследование, многие реализации интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class T,
   class Storage,
   class CreatorClass,
   class ArrayType = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class RowsetInterface = IRowsetImpl <T, IRowset>
>
class CRowsetImpl : 
   public CComObjectRootEx<CreatorClass::_ThreadModel>,
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс пользователя, который является производным от `CRowsetImpl`.

*Хранилища*<br/>
Класс записей пользователя.

*CreatorClass*<br/>
Класс, содержащий свойства для набора строк; Обычно команда.

*ArrayType*<br/>
Класс, который будет выступать в качестве хранилища для данных в наборе строк. Значение по умолчанию `CAtlArray`, но он может быть любой класс, который поддерживает необходимые функциональные возможности.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[NameFromDBID](#namefromdbid)|Извлекает строку из `DBID` и копирует его в *bstr* переданный.|
|[SetCommandText](#setcommandtext)|Проверяет и сохраняет `DBID`s в две строки ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|

### <a name="overridable-methods"></a>Переопределяемые методы

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Извлекает сведения о столбцах для запроса конкретного клиента.|
|[GetCommandFromID](#getcommandfromid)|Проверяет, если оба параметра содержат строковые значения и если да, копирует строковые значения членов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|
|[ValidateCommandID](#validatecommandid)|Проверяет, см. Если параметр или оба `DBID`s содержат строковые значения и если да, копирует их в членах данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_rgRowData](#rgrowdata)|По умолчанию `CAtlArray` , templatizes от аргумента шаблона записей пользователя для `CRowsetImpl`. Другой класс типа массива можно использовать, изменив `ArrayType` аргумент шаблона для `CRowsetImpl`.|
|[m_strCommandText](#strcommandtext)|Содержит команду начального набора строк.|
|[m_strIndexText](#strindextext)|Содержит индекс начального набора строк.|

## <a name="remarks"></a>Примечания

`CRowsetImpl` предоставляет переопределений в виде статических требуемому типу. Методы управлять способом, в котором определенного набора строк будет проверять текст команды. Вы можете создать свой собственный `CRowsetImpl`-класс стиля, сделав реализация интерфейсов нескольких наследуется. Единственный метод, для которого необходимо предоставить реализацию `Execute`. В зависимости от того, какой тип набора строк при создании, создатель методы ожидают различными сигнатурами для `Execute`. Например, если вы используете `CRowsetImpl`-производный класс для реализации набора строк схемы, `Execute` метод будет иметь следующую сигнатуру:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

Если вы создаете `CRowsetImpl`-производный класс для реализации команды или сеанса набора строк, `Execute` метод будет иметь следующую сигнатуру:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

Для реализации любого из `CRowsetImpl`-производным `Execute` методы, необходимо заполнить буферы внутренних данных ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).

## <a name="namefromdbid"></a> CRowsetImpl::NameFromDBID

Извлекает строку из `DBID` и копирует его в *bstr* переданный.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>Параметры

*pDBID*<br/>
[in] Указатель на `DBID` из которого извлекается строка.

*BSTR*<br/>
[in] Объект [CComBSTR](../../atl/reference/ccombstr-class.md) ссылку на поместите копию `DBID` строка.

*bIndex*<br/>
[in] **true** индекс `DBID`; **false** ли таблица `DBID`.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT. Зависимости `DBID` является таблица или индекс (обозначается *bIndex*), либо метод вернет значение DB_E_NOINDEX или DB_E_NOTABLE.

### <a name="remarks"></a>Примечания

Этот метод вызывается `CRowsetImpl` реализации [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).

## <a name="setcommandtext"></a> CRowsetImpl::SetCommandText

Проверяет и сохраняет `DBID`s в две строки ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
[in] Указатель на `DBID` представляющее идентификатор таблицы.

*pIndexID*<br/>
[in] Указатель на `DBID` представляет идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

`SetCommentText` Вызывается метод `CreateRowset`, статический создания шаблона метод `IOpenRowsetImpl`.

Этот метод делегирует свою работу, вызвав [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) через повышенный указатель.

## <a name="getcolumninfo"></a> CRowsetImpl::GetColumnInfo

Извлекает сведения о столбцах для запроса конкретного клиента.

### <a name="syntax"></a>Синтаксис

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>Параметры

*PV*<br/>
[in] Указатель на пользователя `CRowsetImpl` производного класса.

*pcCols*<br/>
[in] Указатель (на выходе) числу столбцов, возвращаемых.

### <a name="return-value"></a>Возвращаемое значение

Указатель на статическую `ATLCOLUMNINFO` структуры.

### <a name="remarks"></a>Примечания

Этот метод является расширенной переопределения.

Этот метод вызывается несколько классов базовую реализацию, чтобы получить сведения о столбцах для запроса конкретного клиента. Как правило, этот метод будет вызываться `IColumnsInfoImpl`. Если вы Переопределите этот метод, необходимо поместить версии метода в вашей `CRowsetImpl`-производного класса. Так как метод может размещаться в классе без создания шаблона, необходимо изменить *pv* к соответствующему `CRowsetImpl`-производного класса.

В следующем примере демонстрируется `GetColumnInfo` использования. В этом примере `CMyRowset` — `CRowsetImpl`-производного класса. Чтобы переопределить `GetColumnInfo` для всех экземпляров этого класса, поместите следующий метод в `CMyRowset` определение класса:

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="getcommandfromid"></a> CRowsetImpl::GetCommandFromID

Проверяет, если оба параметра содержат строковые значения и если да, копирует строковые значения членов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
[in] Указатель на `DBID` представляет идентификатор таблицы.

*pIndexID*<br/>
[in] Указатель на `DBID` представляющий, идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод вызывается через статический восходящее приведение типа с `CRowsetImpl` для заполнения элементов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). По умолчанию этот метод проверяет, см. в разделе, если оба параметра содержат строковые значения. Если они содержат строковые значения, этот метод копирует строковые значения для элементов данных. Поместив метод со следующей сигнатурой в вашей `CRowsetImpl`-производного класса, ваш метод будет вызван вместо базовую реализацию.

## <a name="validatecommandid"></a> CRowsetImpl::ValidateCommandID

Проверяет, см. Если параметр или оба `DBID`s содержат строковые значения и если да, копирует их в членах данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
[in] Указатель на `DBID` представляющее идентификатор таблицы.

*pIndexID*<br/>
[in] Указатель на `DBID` представляет идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод вызывается через статический восходящее приведение типа с `CRowsetImpl` для заполнения его элементов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). По умолчанию этот метод проверяет, см. Если параметр или оба `DBID`s содержат строковые значения и если да, копирует их в элементах данных. Поместив метод со следующей сигнатурой в вашей `CRowsetImpl`-производного класса, ваш метод будет вызван вместо базовую реализацию.

## <a name="rgrowdata"></a> CRowsetImpl::m_rgRowData

По умолчанию `CAtlArray` , templatizes от аргумента шаблона записей пользователя для `CRowsetImpl`.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>Примечания

*ArrayType* параметр шаблона `CRowsetImpl`.

## <a name="strcommandtext"></a> CRowsetImpl::m_strCommandText

Содержит команду начального набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="strindextext"></a> CRowsetImpl::m_strIndexText

Содержит индекс начального набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```