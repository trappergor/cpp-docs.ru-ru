---
title: Глобальные функции сопоставления COM
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: 75d081674fa4b63e66f1296834d3de305665ab9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258420"
---
# <a name="com-map-global-functions"></a>Глобальные функции сопоставления COM

Эти функции обеспечивают поддержку для сопоставления COM `IUnknown` реализаций.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Делегирует `IUnknown` неагрегированные объекта.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Создает эффективного кода для сравнения интерфейсы с параметром `IUnknown`.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface

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
[in] Указатель на объект, содержащий карту COM интерфейсы, предоставляемые в `QueryInterface`.

*pEntries*<br/>
[in] Массив `_ATL_INTMAP_ENTRY` структур, которые обращаются к карту доступных интерфейсов.

*IID*<br/>
[in] Идентификатор GUID запрашиваемого интерфейса.

*ppvObject*<br/>
[out] Указатель на указатель интерфейса, заданный в *iid*, или значение NULL, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`AtlInternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM. Если объект является статистическим, `AtlInternalQueryInterface` не делегировать внешняя Неизвестная строка. Вы можете ввести интерфейсы в таблицу сопоставлений COM с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из его вариантов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown

Вызывайте эту функцию для особого случая тестирования для `IUnknown`.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Параметры

*rguid1*<br/>
[in] Идентификатор GUID для сравнения с `IID_IUnknown`.

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы сопоставления COM](../../atl/reference/com-map-macros.md)
