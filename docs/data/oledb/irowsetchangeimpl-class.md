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
ms.openlocfilehash: ae4ceea53ec91cc3f9593dd3789fcf61e0702274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376944"
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl

Реализация интерфейса [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) в спецификации OLE DB.

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
Класс, полученный `IRowsetChangeImpl`из .

*Память*<br/>
Запись пользователя.

*БазовыйИнтерфейс*<br/>
Базовый класс для интерфейса, например `IRowsetChange`.

*РоуКласс*<br/>
Блок хранения для рукоятки строки.

*КартаКласс*<br/>
Единица хранения для всех строковых декейок, хранятся у поставщика.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)

|||
|-|-|
|[УдалитьСтроки](#deleterows)|Удаляет строки из набора строк.|
|[InsertRow](#insertrow)|Вставляет строку в ряд.|
|[Setdata](#setdata)|Устанавливает значения данных в одном или нескольких столбцах.|

### <a name="implementation-method-callback"></a>Метод реализации (Обратный вызов)

|||
|-|-|
|[ФлешДата](#flushdata)|Переопределяется провайдером для фиксации данных в хранилище.|

## <a name="remarks"></a>Remarks

Этот интерфейс отвечает за немедленную запись операций в хранилище данных. "Немедленно" означает, что, когда конечный пользователь (лицо, использующего потребителя) вносит какие-либо изменения, эти изменения немедленно передаются в хранилище данных (и не могут быть отменены).

`IRowsetChangeImpl`реализует интерфейс OLE `IRowsetChange` DB, который позволяет обновлять значения столбцов в существующих строках, удалять строки и вставлять новые строки.

Реализация ПРОГРАММЫ OLE DB Templates поддерживает`SetData`все `InsertRow`базовые методы (, и `DeleteRows`).

> [!IMPORTANT]
> Настоятельно рекомендуется прочитать следующую документацию, прежде чем пытаться реализовать ваш провайдер:

- [Создание updatable провайдера](../../data/oledb/creating-an-updatable-provider.md)

- Глава 6 *Справочника программиста OLE DB*

- Также посмотрите, `RUpdateRowset` как класс используется в образце [UpdatePV.](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>IRowsetChangeImpl::DeleteRows

Удаляет строки из набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

Смотрите [IRowsetChange::DeleteRows](/previous-versions/windows/desktop/ms724362(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>IRowsetChangeImpl::InsertRow

Создает и инициализирует новую строку в строке.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Параметры

Смотрите [IRowsetChange::InsertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>IRowsetChangeImpl::SetData

Устанавливает значения данных в одном или нескольких столбцах.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Параметры

Смотрите [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>IRowsetChangeImpl::FlushData

Переопределяется провайдером для фиксации данных в хранилище.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Параметры

*hrowToFlush*<br/>
(в) Обработка строк для данных. Тип этой строки определяется из аргумента `IRowsetImpl` шаблона`CSimpleRow` *RowClass* класса (по умолчанию).

*hAccessorToFlush*<br/>
(в) Ручка к аксессуару, который содержит обязательную `PROVIDER_MAP` информацию и информацию о типе в нем (см. [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
