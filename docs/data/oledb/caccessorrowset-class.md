---
title: Класс CAccessorRowset
ms.date: 11/04/2016
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
- CAccessorRowset.Bind
- CAccessorRowset::Bind
- CAccessorRowset::CAccessorRowset
- CAccessorRowset.CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
helpviewer_keywords:
- CAccessorRowset class
- CAccessorRowset class, methods
- CAccessorRowset class, members
- Bind method
- CAccessorRowset class, constructor
- Close method
- FreeRecordMemory method
- GetColumnInfo method
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
ms.openlocfilehash: d9dd2eec3948896487b5b977d1107db1f4a1046b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498715"
---
# <a name="caccessorrowset-class"></a>Класс CAccessorRowset

Инкапсулирует набор строк и связанные с ним методы доступа в одном классе.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset>
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Класс метода доступа.

*тровсет*<br/>
Класс набора строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Элементы

### <a name="methods"></a>Методы

| Имя | Описание |
|--|--|
| [Выполняется](#bind) | Создает привязки (используется, если `bBind` указан как **`false`** в [CCommand:: Open](./ccommand-class.md#open)). |
| [CAccessorRowset](#caccessorrowset) | Конструктор. |
| [Закрыть](#close) | Закрывает набор строк и любые методы доступа. |
| [фрирекордмемори](#freerecordmemory) | Освобождает все столбцы в текущей записи, которые необходимо освободить. |
| [GetColumnInfo](#getcolumninfo) | Реализует [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)). |

## <a name="remarks"></a>Remarks

Класс `TAccessor` управляет методом доступа. Класс *тровсет* управляет набором строк.

## <a name="caccessorrowsetbind"></a><a name="bind"></a> CAccessorRowset:: BIND

Создает привязки, если вы указали `bBind` как **`false`** в элементе [CCommand:: Open](./ccommand-class.md#open).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Bind();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="caccessorrowsetcaccessorrowset"></a><a name="caccessorrowset"></a> CAccessorRowset:: CAccessorRowset

Выполняет инициализацию объекта `CAccessorRowset`.

### <a name="syntax"></a>Синтаксис

```cpp
CAccessorRowset();
```

## <a name="caccessorrowsetclose"></a><a name="close"></a> CAccessorRowset:: Close

Освобождает все активные методы доступа и набор строк.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Remarks

Освобождает любую связанную память.

## <a name="caccessorrowsetfreerecordmemory"></a><a name="freerecordmemory"></a> CAccessorRowset:: Фрирекордмемори

Освобождает все столбцы в текущей записи, которые необходимо освободить.

### <a name="syntax"></a>Синтаксис

```cpp
void FreeRecordMemory();
```

## <a name="caccessorrowsetgetcolumninfo"></a><a name="getcolumninfo"></a> CAccessorRowset:: GetColumnInfo

Возвращает сведения о столбцах из открытого набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,
   DBCOLUMNINFO** ppColumnInfo,
   LPOLESTR* ppStrings) const;

HRESULT GetColumnInfo(DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo);
```

#### <a name="parameters"></a>Параметры

См. раздел [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Пользователь должен освободить информацию о возвращаемом столбце и буфере строк. Используйте вторую версию этого метода при использовании [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) и необходимости переопределения привязок.

Дополнительные сведения см. в разделе [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Справочник по шаблонам потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
