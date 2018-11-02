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
- CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- FreeRecordMemory
- GetColumnInfo
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
ms.openlocfilehash: 78e7bac10bb496e2ff1c270916fc732dbe71d8db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573173"
---
# <a name="caccessorrowset-class"></a>Класс CAccessorRowset

Инкапсулирует набор строк и его связанные методы доступа в одном классе.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset>
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>
```

### <a name="parameters"></a>Параметры

*TAccessor*<br/>
Класс, метод доступа.

*TRowset*<br/>
Класс набора строк.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Bind](#bind)|Создает привязки (используется, когда `bBind` указывается как **false** в [CCommand::Open](../../data/oledb/ccommand-open.md)).|
|[CAccessorRowset](#caccessorrowset)|Конструктор.|
|[Закрыть](#close)|Закрывает набор строк и все методы доступа.|
|[FreeRecordMemory](#freerecordmemory)|Освобождает все столбцы в текущей записи, которые следует освободиться.|
|[GetColumnInfo](#getcolumninfo)|Реализует [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704).|

## <a name="remarks"></a>Примечания

Класс `TAccessor` управляет метода доступа. Класс *TRowset* управляет набора строк.

## <a name="bind"></a> CAccessorRowset::Bind

Создает привязки, если вы указали `bBind` как **false** в [CCommand::Open](../../data/oledb/ccommand-open.md).

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Bind();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="caccessorrowset"></a> CAccessorRowset::CAccessorRowset

Инициализирует `CAccessorRowset` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
CAccessorRowset();
```

## <a name="close"></a> CAccessorRowset::Close

Освобождает все active методы доступа и набор строк.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Освобождает все связанные памяти.

## <a name="freerecordmemory"></a> CAccessorRowset::FreeRecordMemory

Освобождает все столбцы в текущей записи, которые следует освободиться.

### <a name="syntax"></a>Синтаксис

```cpp
void FreeRecordMemory();
```

## <a name="getcolumninfo"></a> CAccessorRowset::GetColumnInfo

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

См. в разделе [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Пользователь должен освободить сведения возвращаемого столбца и строки буфера. Использовать второй версии этого метода при использовании [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) и нужно переопределить привязок.

Дополнительные сведения см. в разделе [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704) в *Справочник программиста OLE DB по*.

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)