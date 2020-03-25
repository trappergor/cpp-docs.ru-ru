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
ms.openlocfilehash: 79d85e7d1c849bcaa7c2aa1b3f6d9d50a20d1b2a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210318"
---
# <a name="irowsetupdateimpl-class"></a>Класс IRowsetUpdateImpl

Реализация OLE DB шаблонов интерфейса [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) .

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
Класс, производный от `IRowsetUpdateImpl`.

*Память*<br/>
Запись пользователя.

*UpdateArray*<br/>
Массив, содержащий кэшированные данные для обновления набора строк.

*ровкласс*<br/>
Единица хранения для `HROW`.

*мапкласс*<br/>
Единица хранения для всех дескрипторов строк, удерживаемых поставщиком.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используются с IRowsetChange)

|||
|-|-|
|[SetData](#setdata)|Задает значения данных в одном или нескольких столбцах.|

### <a name="interface-methods-used-with-irowsetupdate"></a>Методы интерфейса (используются с IRowsetUpdate)

|||
|-|-|
|[жеторигиналдата](#getoriginaldata)|Возвращает данные, которые были переданы в последнее время или получены из источника данных, игнорируя ожидающие изменения.|
|[жетпендингровс](#getpendingrows)|Возвращает список строк с ожидающими изменениями.|
|[жетровстатус](#getrowstatus)|Возвращает состояние указанных строк.|
|[Отменить](#undo)|Отменяет любые изменения в строке с момента последней выборки или обновления.|
|[Update](#update)|Передает все изменения, внесенные в строку с момента последней выборки или обновления.|

### <a name="implementation-methods-callback"></a>Методы реализации (обратный вызов)

|||
|-|-|
|[исупдатеалловед](#isupdateallowed)|Используется для проверки безопасности, целостности и т. д. перед разрешением обновлений.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|Содержит исходные данные для отложенной операции.|

## <a name="remarks"></a>Remarks

Сначала следует прочитать и разобраться в документации по [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)), так как все описанное здесь также применимо. Также следует ознакомиться с главой 6 *справочника по OLE DB программиста* по настройке данных.

`IRowsetUpdateImpl` реализует интерфейс OLE DB `IRowsetUpdate`, который позволяет потребителям откладывать передачу изменений, внесенных с `IRowsetChange` в источник данных, и отменять изменения перед передачей.

> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде чем пытаться реализовать поставщик:

- [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)

- Глава 6 *справочника по OLE DB программисту*

- См. также использование класса `RUpdateRowset` в образце [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) .

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowsetUpdateImpl:: SetData

Задает значения данных в одном или нескольких столбцах.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Remarks

Этот метод переопределяет метод [ировсетчанжеимпл:: SetData](../../data/oledb/irowsetchangeimpl-setdata.md) , но включает кэширование исходных данных, чтобы позволить немедленно или отложенную обработку операции.

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>IRowsetUpdateImpl:: Жеторигиналдата

Возвращает данные, которые были переданы в последнее время или получены из источника данных, игнорируя ожидающие изменения.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>Параметры

См. раздел [IRowsetUpdate:: жеторигиналдата](/previous-versions/windows/desktop/ms709947(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowsetUpdateImpl:: Жетпендингровс

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

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetUpdate:: жетпендингровс](/previous-versions/windows/desktop/ms719626(v=vs.85)).

Другие параметры см. в разделе [IRowsetUpdate:: жетпендингровс](/previous-versions/windows/desktop/ms719626(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [IRowsetUpdate:: жетпендингровс](/previous-versions/windows/desktop/ms719626(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>IRowsetUpdateImpl:: Жетровстатус

Возвращает состояние указанных строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>Параметры

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetUpdate:: жетровстатус](/previous-versions/windows/desktop/ms724377(v=vs.85)).

Другие параметры см. в разделе [IRowsetUpdate:: жетровстатус](/previous-versions/windows/desktop/ms724377(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowsetUpdateImpl:: Undo

Отменяет любые изменения в строке с момента последней выборки или обновления.

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

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

*пкровсундоне*<br/>
заполняет Соответствует параметру *пкровс* в [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

*пргровсундоне*<br/>
окне Соответствует параметру *пргровс* в [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)).

Другие параметры см. в разделе [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowsetUpdateImpl:: Update

Передает все изменения, внесенные в строку с момента последней выборки или обновления.

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

*хресервед*<br/>
окне Соответствует параметру *параметру hChapter* в [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85)).

Другие параметры см. в разделе [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Remarks

Изменения передаются путем вызова [ировсетчанжеимпл:: FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Чтобы изменения вступили в силу, потребитель должен вызвать метод [CRowset:: Update](../../data/oledb/crowset-update.md) . Задайте для *пргровстатус* соответствующее значение, как описано в разделе [состояния строк](/previous-versions/windows/desktop/ms722752(v=vs.85)) в *справочнике по OLE DB программиста*.

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowsetUpdateImpl:: Исупдатеалловед

Переопределите этот метод, чтобы проверить безопасность, целостность и т. д. перед обновлением.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>Параметры

*status*<br/>
окне Состояние ожидающих операций в строках.

*хровупдате*<br/>
окне Обрабатывает строки, которые пользователь хочет обновить.

*провстатус*<br/>
заполняет Состояние, возвращенное пользователю.

### <a name="remarks"></a>Remarks

Если вы определили, что обновление должно быть разрешено, возвращает S_OK; в противном случае возвращает E_FAIL. Если вы разрешаете обновление, необходимо также задать `DBROWSTATUS` в [IRowsetUpdateImpl:: Update](../../data/oledb/irowsetupdateimpl-update.md) до соответствующего [состояния строки](/previous-versions/windows/desktop/ms722752(v=vs.85)).

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowsetUpdateImpl:: m_mapCachedData

Схема, содержащая исходные данные для отложенной операции.

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
Обработчик строк для данных.

*pData*<br/>
Указатель на данные для кэширования. Данные имеют тип *хранилища* (класс записи пользователя). См. аргумент шаблона *хранилища* в [классе IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md).

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)
