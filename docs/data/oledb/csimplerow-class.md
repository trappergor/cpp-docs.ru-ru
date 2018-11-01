---
title: Класс CSimpleRow
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- CSimpleRow
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: 478e988b350a4e52935838465004cf77f5c1e177
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539494"
---
# <a name="csimplerow-class"></a>Класс CSimpleRow

Предоставляет реализацию по умолчанию для дескриптора строки, которая используется в [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) класса.

## <a name="syntax"></a>Синтаксис

```cpp
class CSimpleRow
```

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AddRefRow](#addrefrow)|Добавляет счетчик ссылок в дескриптор существующей строки.|
|[Compare](#compare)|Сравнивает две строки, чтобы увидеть, если они ссылаются на один и тот же экземпляр строки.|
|[CSimpleRow](#csimplerow)|Конструктор.|
|[ReleaseRow](#releaserow)|Высвобождает строки.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_dwRef](#dwref)|Счетчик ссылок в дескриптор существующей строки.|
|[m_iRowset](#irowset)|Индекс для строк, представляющий курсор.|

## <a name="remarks"></a>Примечания

Дескриптор строки логически является уникальный маркер для строки результата. `IRowsetImpl` Создает новый `CSimpleRow` для каждой строки запроса в [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` Можно также заменить на собственную реализацию маркер строки, как аргумент шаблона по умолчанию для `IRowsetImpl`. Единственное требование для замены этого класса заключается в том, чтобы создать конструктор, который принимает один параметр типа класс замены **LONG**.

## <a name="addrefrow"></a> CSimpleRow::AddRefRow

Добавляет счетчик ссылок в дескриптор существующей строки в потокобезопасным способом.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD AddRefRow();
```

## <a name="compare"></a> CSimpleRow::Compare

Сравнивает две строки, чтобы увидеть, если они ссылаются на один и тот же экземпляр строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>Параметры

*pRow*<br/>
Указатель на объект `CSimpleRow` .

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT, обычно S_OK, указывающее, две строки имеют один и тот же экземпляр строки, или значение S_FALSE, указывающее, две строки различаются. См. в разделе [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629) в *Справочник программиста OLE DB по* другие возможные возвращаемые значения.

## <a name="csimplerow"></a> CSimpleRow::CSimpleRow

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>Параметры

*iRowsetCur*<br/>
[in] Индекс текущего набора строк.

### <a name="remarks"></a>Примечания

Наборы [m_iRowset](../../data/oledb/csimplerow-m-irowset.md) для *iRowsetCur*.

## <a name="releaserow"></a> CSimpleRow::ReleaseRow

Высвобождает строки в потокобезопасным способом.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD ReleaseRow();
```

## <a name="dwref"></a> CSimpleRow::m_dwRef

Счетчик ссылок в дескриптор существующей строки.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD m_dwRef;
```

## <a name="irowset"></a> CSimpleRow::m_iRowset

Индекс для строк, представляющий курсор.

### <a name="syntax"></a>Синтаксис

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)