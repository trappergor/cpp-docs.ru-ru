---
title: Класс IRowsetNotifyCP
ms.date: 11/04/2016
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
ms.openlocfilehash: 481c2c0ec28972e9cef8d1103e49afa2037c2393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544570"
---
# <a name="irowsetnotifycp-class"></a>Класс IRowsetNotifyCP

Реализует сайт поставщика для интерфейса точки подключения [IRowsetNotify клиента](/previous-versions/windows/desktop/ms712959(v=vs.85)).

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>
class IRowsetNotifyCP :
   public IConnectionPointImpl<
      T,
      piid = &__uuidof(IRowsetNotify),
      CComDynamicUnkArray DynamicUnkArray>,
   public ReentrantEventSync
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetNotifyCP`.

*ринтрантевентсинк*<br/>
Класс мьютекса, поддерживающий повторный вход (значение по умолчанию — `CComSharedMutex`). Мьютекс — это объект синхронизации, позволяющий одному потоку взаимно исключать доступ к ресурсу.

*пиид*<br/>
Указатель идентификатора интерфейса (`IID*`) для интерфейса точки подключения `IRowsetNotify`. Значение по умолчанию — `&__uuidof(IRowsetNotify)`.

*динамикункаррай*<br/>
Массив типа [ккомдинамикункаррай](../../atl/reference/ccomdynamicunkarray-class.md), который является динамически выделенным массивом `IUnknown`ных указателей на интерфейсы приемника клиента.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|Сообщает потребителю об изменении значения столбца.|
|[Fire_OnRowChange](#onrowchange)|Уведомляет потребителя об изменении, влияющем на строки.|
|[Fire_OnRowsetChange](#onrowsetchange)|Уведомляет потребителя об изменении, влияющем на весь набор строк.|

## <a name="remarks"></a>Примечания

`IRowsetNotifyCP` реализует широковещательные функции для уведомления прослушивателей на точке подключения `IID_IRowsetNotify` изменения содержимого набора строк.

Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на потребителе (также называемом "приемником") с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , чтобы потребитель мог управлять уведомлениями. См. статью [Получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации интерфейса точки подключения на потребителе.

Подробные сведения о реализации уведомлений см. в разделе "Поддержка уведомлений" раздела [Создание обновляемого поставщика](../../data/oledb/creating-an-updatable-provider.md).

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a>IRowsetNotifyCP:: Fire_OnFieldChange

Передает событие [онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)) , чтобы уведомить потребителей об изменении значения столбца.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,
   HROW hRow,
   DBORDINAL cColumns,
   DBORDINAL* rgColumns,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetNotify клиента:: онфиелдчанже](/previous-versions/windows/desktop/ms715961(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a>IRowsetNotifyCP:: Fire_OnRowChange

Передает событие [онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85)) всем прослушивателям на точке подключения `IID_IRowsetNotify` для уведомления потребителей об изменении, затрагивающих строки.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetNotify клиента:: онровчанже](/previous-versions/windows/desktop/ms722694(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a>IRowsetNotifyCP:: Fire_OnRowsetChange

Передает событие [онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)) всем прослушивателям на точке подключения `IID_IRowsetNotify` для уведомления потребителей об изменении, затрагивающих весь набор строк.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetNotify клиента:: онровсетчанже](/previous-versions/windows/desktop/ms722669(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также:

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Уведомления (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)