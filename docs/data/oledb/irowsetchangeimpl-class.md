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
- SetData
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
ms.openlocfilehash: 299cebd93a3d54ab747f5c58b22dbbf215a02e4c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426658"
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl

Реализация шаблонов OLE DB [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) интерфейс в спецификации OLE DB.

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

*Хранилища*<br/>
Записи пользователя.

*BaseInterface*<br/>
Базовый класс для интерфейса, такие как `IRowsetChange`.

*RowClass*<br/>
Единица хранения для дескриптора строки.

*MapClass*<br/>
Единица хранения для всех дескрипторов строк, удерживаемые поставщика.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)

|||
|-|-|
|[DeleteRows](#deleterows)|Удаляет строки из набора строк.|
|[InsertRow](#insertrow)|Вставляет строку в наборе строк.|
|[SetData](#setdata)|Задает значения данных в один или несколько столбцов.|

### <a name="implementation-method-callback"></a>Реализация метода (обратный вызов)

|||
|-|-|
|[FlushData](#flushdata)|Переопределенная поставщиком для фиксации данных в хранилище.|

## <a name="remarks"></a>Примечания

Этот интерфейс отвечает за операции записи немедленно в хранилище данных. «Немедленно» означает, что когда конечный пользователь (пользователь, с помощью потребителя) делает все изменения, эти изменения немедленно переносятся данные хранения (и не может быть отменена).

`IRowsetChangeImpl` реализует OLE DB `IRowsetChange` интерфейс, позволяющий обновлять значения столбцов в существующих строках, удаление строк и вставки новых строк.

Реализация шаблонов OLE DB поддерживает все базовые методы (`SetData`, `InsertRow`, и `DeleteRows`).

> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:

- [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)

- Глава 6 *справочнике программиста OLE DB*

- Также см. в разделе как `RUpdateRowset` класс используется в [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) образца.

## <a name="deleterows"></a> IRowsetChangeImpl::DeleteRows

Удаляет строки из набора строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetChange::DeleteRows](/previous-versions/windows/desktop/ms724362(v=vs.85)(v%3dvs.85)) в *справочнике программиста OLE DB*.

## <a name="insertrow"></a> IRowsetChangeImpl::InsertRow

Создает и инициализирует новую строку в наборе строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetChange::InsertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="setdata"></a> IRowsetChangeImpl::SetData

Задает значения данных в один или несколько столбцов.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="flushdata"></a> IRowsetChangeImpl::FlushData

Переопределенная поставщиком для фиксации данных в хранилище.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Параметры

*hRowToFlush*<br/>
[in] Дескриптор строки данных. Тип этой строки будет определяться *RowClass* аргумент шаблона `IRowsetImpl` класс (`CSimpleRow` по умолчанию).

*hAccessorToFlush*<br/>
[in] Дескриптор метода доступа, который содержит сведения о привязке и сведения о типе в его `PROVIDER_MAP` (см. в разделе [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)