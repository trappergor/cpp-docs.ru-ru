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
ms.openlocfilehash: 66b7607eb28392196f6b7d3790aee976a861f2b6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545615"
---
# <a name="carrayrowset-class"></a>Класс CArrayRowset

Обращается к элементам набора строк с помощью синтаксиса Array.

## <a name="syntax"></a>Синтаксис

```cpp
template < class TAccessor >
class CArrayRowset :
   public CVirtualBuffer <TAccessor>,
   protected CBulkRowset <TAccessor>
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Тип класса метода доступа, который должен использоваться набором строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[CArrayRowset](#carrayrowset)|Конструктор.|
|[Моментальный снимок](#snapshot)|Считывает весь набор строк в память.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Станции&#91;&#93;](#operator)|Обращается к элементу набора строк.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[CArrayRowset::m_nRowsRead](#nrowsread)|Число уже считанных строк.|

## <a name="carrayrowsetcarrayrowset"></a><a name="carrayrowset"></a>CArrayRowset:: CArrayRowset

Создает новый объект типа `CArrayRowset`.

### <a name="syntax"></a>Синтаксис

```cpp
CArrayRowset(int nMax = 100000);
```

#### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
окне Максимальное число строк в наборе строк.

## <a name="carrayrowsetsnapshot"></a><a name="snapshot"></a>CArrayRowset:: snapshot

Считывает весь набор строк в память, создавая изображение или его снимок.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Snapshot() throw();
```

## <a name="carrayrowsetoperator"></a><a name="operator"></a>CArrayRowset:: operator

Предоставляет синтаксис, подобный массиву, для доступа к строке в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
TAccessor & operator[](int nrow);
```

#### <a name="parameters"></a>Параметры

*такцессор*<br/>
Шаблонный параметр, указывающий тип метода доступа, хранящегося в наборе строк.

*нров*<br/>
окне Номер строки (элемента массива), к которой требуется получить доступ.

### <a name="return-value"></a>Возвращаемое значение

Содержимое запрошенной строки.

### <a name="remarks"></a>Примечания

Если *нров* превышает количество строк в наборе строк, возникает исключение.

## <a name="carrayrowsetm_nrowsread"></a><a name="nrowsread"></a>CArrayRowset:: m_nRowsRead

Содержит количество строк в наборе строк, которые уже считаны.

### <a name="syntax"></a>Синтаксис

```cpp
ULONG m_nRowsRead;
```

## <a name="see-also"></a>См. также:

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CRowset](../../data/oledb/crowset-class.md)