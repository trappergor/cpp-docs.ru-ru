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
ms.openlocfilehash: 956648babf987d156cac753f8373518a83362013
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079678"
---
# <a name="crowsetimpl-class"></a>Класс CRowsetImpl

Предоставляет стандартную реализацию набора строк OLE DB, не требуя множественного наследования многих интерфейсов реализации.

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
Класс пользователя, производный от `CRowsetImpl`.

*Память*<br/>
Класс записей пользователя.

*креаторкласс*<br/>
Класс, содержащий свойства для набора строк; Обычно это команда.

*ArrayType*<br/>
Класс, который будет использоваться как хранилище для данных набора строк. По умолчанию этот параметр имеет значение `CAtlArray`, но может быть любым классом, поддерживающим необходимые функции.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[намефромдбид](#namefromdbid)|Извлекает строку из `DBID` и копирует ее в переданный объект *BSTR* .|
|[SetCommandText](#setcommandtext)|Проверяет и сохраняет `DBID`s в двух строках ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|

### <a name="overridable-methods"></a>Переопределяемые методы

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Возвращает сведения о столбце для конкретного запроса клиента.|
|[жеткоммандфромид](#getcommandfromid)|Проверяет, содержат ли один или оба параметра строковые значения, и, если да, копирует строковые значения в элементы данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|
|[валидатекоммандид](#validatecommandid)|Проверяет, содержат ли или оба `DBID`строковые значения, и, если да, копирует их в члены данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_rgRowData](#rgrowdata)|По умолчанию `CAtlArray`, темплатизес в аргументе шаблона записи пользователя для `CRowsetImpl`. Другой класс типа массива можно использовать, изменив аргумент шаблона `ArrayType` на `CRowsetImpl`.|
|[m_strCommandText](#strcommandtext)|Содержит начальную команду набора строк.|
|[m_strIndexText](#strindextext)|Содержит начальный индекс набора строк.|

## <a name="remarks"></a>Примечания

`CRowsetImpl` предоставляет переопределения в виде статических преобразований. Методы управляют способом, которым данный набор строк будет проверять текст команды. Вы можете создать собственный класс `CRowsetImpl`, сделав интерфейсы реализации множественно наследуемыми. Единственный метод, для которого необходимо предоставить реализацию, — это `Execute`. В зависимости от типа создаваемого набора строк методы Creator будут иметь разные сигнатуры для `Execute`. Например, если для реализации набора строк схемы используется производный от `CRowsetImpl`класс, метод `Execute` будет иметь следующую сигнатуру:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

При создании класса, производного от `CRowsetImpl`, для реализации набора строк команды или сеанса метод `Execute` будет иметь следующую сигнатуру:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

Для реализации любого из методов `Execute`, производных от `CRowsetImpl`, необходимо заполнить внутренние буферы данных ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).

## <a name="crowsetimplnamefromdbid"></a><a name="namefromdbid"></a>CRowsetImpl:: Намефромдбид

Извлекает строку из `DBID` и копирует ее в переданный объект *BSTR* .

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>Параметры

*пдбид*<br/>
окне Указатель на `DBID`, из которого извлекается строка.

*освобождаемой*<br/>
окне Ссылка на [CComBSTR](../../atl/reference/ccombstr-class.md) для размещения копии `DBID` строки.

*биндекс*<br/>
окне **значение true** , если индекс `DBID`; **значение false** , если таблица `DBID`.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. В зависимости от того, является ли `DBID` таблицей или индексом (обозначено *биндекс*), метод возвратит значение DB_E_NOINDEX или DB_E_NOTABLE.

### <a name="remarks"></a>Примечания

Этот метод вызывается `CRowsetImpl` реализациями [валидатекоммандид](../../data/oledb/crowsetimpl-validatecommandid.md) и [жеткоммандфромид](../../data/oledb/crowsetimpl-getcommandfromid.md).

## <a name="crowsetimplsetcommandtext"></a><a name="setcommandtext"></a>CRowsetImpl:: SetCommandText

Проверяет и сохраняет `DBID`s в двух строках ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
окне Указатель на `DBID`, представляющий идентификатор таблицы.

*pIndexID*<br/>
окне Указатель на `DBID`, представляющий идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Метод `SetCommentText` вызывается `CreateRowset`, статическим методом преобразованный `IOpenRowsetImpl`.

Этот метод делегирует свою работу, вызывая [валидатекоммандид](../../data/oledb/crowsetimpl-validatecommandid.md) и [жеткоммандфромид](../../data/oledb/crowsetimpl-getcommandfromid.md) с помощью преобразованного указателя.

## <a name="crowsetimplgetcolumninfo"></a><a name="getcolumninfo"></a>CRowsetImpl:: GetColumnInfo

Возвращает сведения о столбце для конкретного запроса клиента.

### <a name="syntax"></a>Синтаксис

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>Параметры

*PV*<br/>
окне Указатель на производный класс `CRowsetImpl` пользователя.

*пкколс*<br/>
окне Указатель (вывод) на число возвращаемых столбцов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на статическую структуру `ATLCOLUMNINFO`.

### <a name="remarks"></a>Примечания

Этот метод является расширенным переопределением.

Этот метод вызывается несколькими базовыми классами реализации для получения сведений о столбцах для конкретного запроса клиента. Обычно этот метод вызывается `IColumnsInfoImpl`. При переопределении этого метода необходимо поместить версию метода в класс, производный от `CRowsetImpl`. Поскольку метод может быть помещен в класс, не являющийся преобразованный, необходимо изменить *НЗ* на соответствующий класс, производный от `CRowsetImpl`.

В следующем примере демонстрируется использование `GetColumnInfo`. В этом примере `CMyRowset` является производным от `CRowsetImpl`классом. Чтобы переопределить `GetColumnInfo` для всех экземпляров этого класса, поместите следующий метод в определение класса `CMyRowset`:

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="crowsetimplgetcommandfromid"></a><a name="getcommandfromid"></a>CRowsetImpl:: Жеткоммандфромид

Проверяет, содержат ли один или оба параметра строковые значения, и, если да, копирует строковые значения в элементы данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
окне Указатель на `DBID`, представляющий идентификатор таблицы.

*pIndexID*<br/>
окне Указатель на `DBID`, представляющий идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод вызывается с помощью статического предадресного `CRowsetImpl` для заполнения элементов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). По умолчанию этот метод проверяет, содержат ли один или оба параметра строковые значения. Если они содержат строковые значения, этот метод копирует строковые значения в элементы данных. Поместив метод с этой сигнатурой в класс, производный от `CRowsetImpl`, метод будет вызываться вместо базовой реализации.

## <a name="crowsetimplvalidatecommandid"></a><a name="validatecommandid"></a>CRowsetImpl:: Валидатекоммандид

Проверяет, содержат ли или оба `DBID`строковые значения, и, если да, копирует их в члены данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Параметры

*pTableID*<br/>
окне Указатель на `DBID`, представляющий идентификатор таблицы.

*pIndexID*<br/>
окне Указатель на `DBID`, представляющий идентификатор индекса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод вызывается с помощью статического предадресного `CRowsetImpl` для заполнения его элементов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). По умолчанию этот метод проверяет, содержат ли или оба `DBID`строковые значения, и, если да, копирует их в элементы данных. Поместив метод с этой сигнатурой в класс, производный от `CRowsetImpl`, метод будет вызываться вместо базовой реализации.

## <a name="crowsetimplm_rgrowdata"></a><a name="rgrowdata"></a>CRowsetImpl:: m_rgRowData

По умолчанию `CAtlArray`, темплатизес в аргументе шаблона записи пользователя для `CRowsetImpl`.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>Примечания

*ArrayType* — это параметр шаблона для `CRowsetImpl`.

## <a name="crowsetimplm_strcommandtext"></a><a name="strcommandtext"></a>CRowsetImpl:: m_strCommandText

Содержит начальную команду набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="crowsetimplm_strindextext"></a><a name="strindextext"></a>CRowsetImpl:: m_strIndexText

Содержит начальный индекс набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```