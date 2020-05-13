---
title: Класс IRowsetUpdateImpl
ms.date: 11/04/2016
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
ms.openlocfilehash: 6347a42b9065239f768c6b50c430946393358df1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370749"
---
# <a name="irowsetupdateimpl-class"></a>Класс IRowsetUpdateImpl

Реализация интерфейса [ИНТЕРФЕЙСа IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) выполнена в комплектациях OLE DB.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   class T,
   class Storage,
   class UpdateArray = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>
>

class IRowsetUpdateImpl : public IRowsetChangeImpl<
   T,
   Storage,
   IRowsetUpdate,
   RowClass,
   MapClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, полученный `IRowsetUpdateImpl`из .

*Память*<br/>
Запись пользователя.

*ОбновлениеРейрей*<br/>
Массив, содержащий кэшированные данные для обновления строки.

*РоуКласс*<br/>
Единица хранения `HROW`для .

*КартаКласс*<br/>
Единица хранения для всех строковых декейок, хранятся у поставщика.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)

|||
|-|-|
|[Setdata](#setdata)|Устанавливает значения данных в одном или нескольких столбцах.|

### <a name="interface-methods-used-with-irowsetupdate"></a>Методы интерфейса (используется с IRowsetUpdate)

|||
|-|-|
|[GetOriginalData](#getoriginaldata)|Получает данные совсем недавно переданных или полученных из источника данных, игнорируя ожидающие изменения.|
|[GetPendingRows](#getpendingrows)|Возвращает список строк с ожидающими изменениями.|
|[ГетРоуСтатусстом](#getrowstatus)|Возвращает статус указанных строк.|
|[Отменить](#undo)|Отменяет любые изменения в строке с момента последнего получения или обновления.|
|[Обновление](#update)|Передает любые изменения, внесенные в строку с момента последнего получения или обновления.|

### <a name="implementation-methods-callback"></a>Методы реализации (Обратный вызов)

|||
|-|-|
|[Обновление Разрешено](#isupdateallowed)|Используется для проверки безопасности, целостности и так далее, прежде чем разрешить обновления.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|Содержит исходные данные для отложенной операции.|

## <a name="remarks"></a>Remarks

Вы должны сначала прочитать и понять документацию для [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)), потому что все, что описано там также относится здесь. Вы также должны прочитать главу 6 *ссылки программиста OLE DB* на настройку данных.

`IRowsetUpdateImpl`реализует интерфейс OLE `IRowsetUpdate` DB, который позволяет потребителям задерживать `IRowsetChange` передачу изменений, внесенных в источник данных, и отменить изменения перед передачей.

> [!IMPORTANT]
> Настоятельно рекомендуется прочитать следующую документацию, прежде чем пытаться реализовать ваш провайдер:

- [Создание updatable провайдера](../../data/oledb/creating-an-updatable-provider.md)

- Глава 6 *Справочника программиста OLE DB*

- Также посмотрите, `RUpdateRowset` как класс используется в образце [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowsetUpdateImpl::SetData

Устанавливает значения данных в одном или нескольких столбцах.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Параметры

Смотрите [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) в *справке программиста OLE DB*.

### <a name="remarks"></a>Remarks

Этот метод переопределяет метод [IRowsetChangeImpl::SetData,](../../data/oledb/irowsetchangeimpl-setdata.md) но включает кэширование исходных данных, чтобы позволить немедленную или отложенную обработку операции.

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>IRowsetUpdateImpl::GetOriginalData

Получает данные совсем недавно переданных или полученных из источника данных, игнорируя ожидающие изменения.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>Параметры

Смотрите [IRowsetUpdate::GetOriginalData](/previous-versions/windows/desktop/ms709947(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowsetUpdateImpl::GetPendingRows

Возвращает список строк с ожидающими изменениями.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,
   DBPENDINGSTATUS dwRowStatus,
   DBCOUNTITEM* pcPendingRows,
   HROW** prgPendingRows,
   DBPENDINGSTATUS** prgPendingStatus);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
(в) Соответствует параметру *hChapter* в [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)).

Для других параметров, [см. IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) в *справке программиста OLE DB*.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации см. [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>IRowsetUpdateImpl::GetRowStatus

Возвращает статус указанных строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
(в) Соответствует параметру *hChapter* в [IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)).

Для других параметров [см. IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowsetUpdateImpl::Undo

Отменяет любые изменения в строке с момента последнего получения или обновления.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Undo )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[ ],
   DBCOUNTITEM* pcRowsUndone,
   HROW** prgRowsUndone,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
(в) Соответствует параметру *hChapter* в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

*pcRowsUndone*<br/>
(ваут) Соответствует параметру *pcRows* в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

*prgRowsUndone*<br/>
(в) Соответствует параметру *prgRows* в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

Для других параметров [см. IRowsetUpdate::Отменить](/previous-versions/windows/desktop/ms719655(v=vs.85)) *ссылку программиста OLE DB.*

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowsetUpdateImpl::Обновление

Передает любые изменения, внесенные в строку с момента последнего получения или обновления.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Update )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBCOUNTITEM* pcRows,
   HROW** prgRows,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
(в) Соответствует параметру *hChapter* в [IRowsetUpdate::Обновление](/previous-versions/windows/desktop/ms719709(v=vs.85)).

Для других параметров [см. IRowsetUpdate::Update](/previous-versions/windows/desktop/ms719709(v=vs.85)) в *справке программиста OLE DB*.

### <a name="remarks"></a>Remarks

Изменения передаются по телефону [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Потребитель должен позвонить [cRowset::Обновление](../../data/oledb/crowset-update.md) для изменений, чтобы вступили в силу. Установите *prgRowstatus* на соответствующее значение, как описано в [строке государств](/previous-versions/windows/desktop/ms722752(v=vs.85)) в *справке программиста OLE DB*.

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowsetUpdateImpl::ОбновлениеРазрешено

Переопределить этот метод, чтобы проверить безопасность, целостность и так далее перед обновлениями.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>Параметры

*состояние*<br/>
(в) Состояние ожидающих операций на строках.

*hRowUpdate*<br/>
(в) Ручка для строк, которые пользователь хочет обновить.

*pRowStatus*<br/>
(ваут) Статус вернулся пользователю.

### <a name="remarks"></a>Remarks

Если вы решите, что обновление должно быть разрешено, возвращается S_OK; в противном случае возвращается E_FAIL. Если вы разрешаете обновление, необходимо `DBROWSTATUS` также установить в [IRowsetUpdateImpl::Обновление](../../data/oledb/irowsetupdateimpl-update.md) соответствующего [состояния строки.](/previous-versions/windows/desktop/ms722752(v=vs.85))

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData

Карта, содержащая исходные данные для отложенной операции.

### <a name="syntax"></a>Синтаксис

```cpp
CAtlMap<
   HROW hRow,
   Storage* pData
>
m_mapCachedData;
```

#### <a name="parameters"></a>Параметры

*hRow*<br/>
Обработка строк для данных.

*Pdata*<br/>
Указатель на данные, которые будут кэшированы. Данные имеют тип *хранения* (класс записи пользователя). Смотрите аргумент *шаблона хранения* в [классе IRowsetUpdateImpl.](../../data/oledb/irowsetupdateimpl-class.md)

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание updatable провайдера](../../data/oledb/creating-an-updatable-provider.md)
