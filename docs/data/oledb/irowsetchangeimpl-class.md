---
title: Класс IRowsetChangeImpl
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: 1e07289a2d0fb283a20657797db5f915c06a39ad
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545903"
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl

OLE DB шаблонов реализации интерфейса [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) в спецификации OLE DB.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetChangeImpl`.

*Память*<br/>
Запись пользователя.

*BaseInterface*<br/>
Базовый класс для интерфейса, например `IRowsetChange`.

*ровкласс*<br/>
Единица хранения для маркера строки.

*мапкласс*<br/>
Единица хранения для всех дескрипторов строк, удерживаемых поставщиком.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используются с IRowsetChange)

|||
|-|-|
|[DeleteRows](#deleterows)|Удаляет строки из набора строк.|
|[InsertRow](#insertrow)|Вставляет строку в набор строк.|
|[SetData](#setdata)|Задает значения данных в одном или нескольких столбцах.|

### <a name="implementation-method-callback"></a>Метод реализации (обратный вызов)

|||
|-|-|
|[FlushData](#flushdata)|Переопределено поставщиком для фиксации данных в хранилище.|

## <a name="remarks"></a>Примечания

Этот интерфейс отвечает за немедленное выполнение операций записи в хранилище данных. "Immediate" означает, что когда конечный пользователь (человек, использующий потребитель) вносит изменения, эти изменения немедленно передаются в хранилище данных (и их нельзя отменить).

`IRowsetChangeImpl` реализует интерфейс OLE DB `IRowsetChange`, который позволяет обновлять значения столбцов в существующих строках, удалять строки и вставлять новые строки.

Реализация шаблонов OLE DB поддерживает все базовые методы (`SetData`, `InsertRow`и `DeleteRows`).

> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде чем пытаться реализовать поставщик:

- [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)

- Глава 6 *справочника по OLE DB программисту*

- Также посмотрите, как в образце [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) используется класс `RUpdateRowset`.

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>Ировсетчанжеимпл::D Елетеровс

Удаляет строки из набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetChange::D елетеровс](/previous-versions/windows/desktop/ms724362(v=vs.85)) в *справочнике по программисту OLE DB*.

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>Ировсетчанжеимпл:: InsertRow

Создает и инициализирует новую строку в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetChange:: insertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>Ировсетчанжеимпл:: SetData

Задает значения данных в одном или нескольких столбцах.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>Ировсетчанжеимпл:: FlushData

Переопределено поставщиком для фиксации данных в хранилище.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Параметры

*хровтофлуш*<br/>
окне Обработчик строк для данных. Тип этой строки определяется из аргумента шаблона *ровкласс* класса `IRowsetImpl` (по умолчанию`CSimpleRow`).

*хакцессортофлуш*<br/>
окне Обработчик метода доступа, который содержит сведения о привязке и сведения о типе в своем `PROVIDER_MAP` (см. [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также:

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)