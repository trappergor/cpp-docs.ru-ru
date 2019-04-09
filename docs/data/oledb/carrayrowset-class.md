---
title: Класс CArrayRowset
ms.date: 11/04/2016
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
ms.openlocfilehash: b257c4e95a99bfbc8042c5935638a70deac0ea7a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040242"
---
# <a name="carrayrowset-class"></a>Класс CArrayRowset

Обращений к элементы набора строк с помощью синтаксиса массива.

## <a name="syntax"></a>Синтаксис

```cpp
template < class TAccessor >
class CArrayRowset :
   public CVirtualBuffer <TAccessor>,
   protected CBulkRowset <TAccessor>
```

### <a name="parameters"></a>Параметры

*TAccessor*<br/>
Тип метода доступа класса, который вы хотите использовать набор строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CArrayRowset](#carrayrowset)|Конструктор.|
|[Снимок](#snapshot)|Считывает всего набора строк в памяти.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор&#91;&#93;](#operator)|Обращается к элементу набора строк.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[CArrayRowset::m_nRowsRead](#nrowsread)|Номер строки, уже считанные.|

## <a name="carrayrowset"></a> CArrayRowset::CArrayRowset

Создает новый объект `CArrayRowset`.

### <a name="syntax"></a>Синтаксис

```cpp
CArrayRowset(int nMax = 100000);
```

#### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
[in] Максимальное число строк в наборе строк.

## <a name="snapshot"></a> CArrayRowset::Snapshot

Считывает всего набора строк в памяти, создания образа или моментального снимка его.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Snapshot() throw();
```

## <a name="operator"></a> CArrayRowset::operator

Предоставляет синтаксис, подобный массиву для доступа к строке в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
TAccessor & operator[](int nrow);
```

#### <a name="parameters"></a>Параметры

*TAccessor*<br/>
Параметр шаблона, указывающее тип метода доступа, хранящиеся в наборе строк.

*nRow*<br/>
[in] Номер строки (элемент массива), необходимо получить доступ.

### <a name="return-value"></a>Возвращаемое значение

Содержимое Запрошенная строка.

### <a name="remarks"></a>Примечания

Если *nRow* превышает число строк в наборе строк, возникает исключение.

## <a name="nrowsread"></a> CArrayRowset::m_nRowsRead

Содержит количество строк в наборе строк, которые уже были считаны.

### <a name="syntax"></a>Синтаксис

```cpp
ULONG m_nRowsRead;
```

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CRowset](../../data/oledb/crowset-class.md)