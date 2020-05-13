---
title: COM Карта Глобальные функции
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: c4ce7c7a68c0744ad65ef4914088fa12d3340628
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326695"
---
# <a name="com-map-global-functions"></a>COM Карта Глобальные функции

Эти функции обеспечивают `IUnknown` поддержку реализации COM Map.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Делегаты `IUnknown` неагрегированного объекта.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Генерирует эффективный код для `IUnknown`сравнения интерфейсов с .|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>АтлИнтеркеиЕРиИнтерфейс

Извлекает указатель на запрошенный интерфейс.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*pThis*<br/>
(в) Указатель на объект, содержащий карту интерфейсов `QueryInterface`COM, подверженных.

*pE записи*<br/>
(в) Массив `_ATL_INTMAP_ENTRY` структур, которые получают доступ к карте доступных интерфейсов.

*Iid*<br/>
(в) GUID запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, указанный в *iid,* или NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

`AtlInternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если ваш объект агрегирован, `AtlInternalQueryInterface` не делегирует внешнему неизвестному. Вы можете ввести интерфейсы в таблицу карты COM с [макро-COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одним из его вариантов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>InlineisEqualIНеизвестный

Назовите эту функцию, `IUnknown`для специального случая тестирования для .

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Параметры

*rguid1*<br/>
(в) GUID для сравнения `IID_IUnknown`с .

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[COM Карта Макрос](../../atl/reference/com-map-macros.md)
