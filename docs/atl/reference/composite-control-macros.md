---
title: Композитные макросы управления
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 67ad18c07a92cfecca44667908a8488e8c2da234
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331516"
---
# <a name="composite-control-macros"></a>Композитные макросы управления

Эти макросы определяют карты и записи опоглотителей событий.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|Отмечает начало карты раковины события для композитного управления.|
|[END_SINK_MAP](#end_sink_map)|Отметки конца карты раковины события для композитного управления.|
|[SINK_ENTRY](#sink_entry)|Вход на карту раковины события.|
|[SINK_ENTRY_EX](#sink_entry_ex)|Вход на карту раковины события с дополнительным параметром.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Визуальная студия 2017) Подобно SINK_ENTRY_EX за исключением того, что он принимает указатель на iid.|
|[SINK_ENTRY_INFO](#sink_entry_info)|Вход на карту раковины события с вручную поставляемой информацией типа для использования с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Визуальная студия 2017) Подобно SINK_ENTRY_INFO за исключением того, что он принимает указатель на iid.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a>BEGIN_SINK_MAP

Объявляет начало карты раковины события для композитного управления.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>Параметры

*_class*<br/>
(в) Определяет элементуправления.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Remarks

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

## <a name="end_sink_map"></a><a name="end_sink_map"></a>END_SINK_MAP

Объявляет конец карты раковины события для композитного управления.

```
END_SINK_MAP()
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Remarks

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

## <a name="sink_entry"></a><a name="sink_entry"></a>SINK_ENTRY

Объявляет функцию обработчика *(fn*) для указанного события *(dispid),* элемента управления, идентифицированного *id.*

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентифицирует элемент управления.

*Dispid*<br/>
(в) Определяет указанное событие.

*Fn*<br/>
(в) Название функции обработчика событий. Эта функция должна `_stdcall` использовать вызываемую конвенцию и иметь соответствующую подпись в стиле dispinterface.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Remarks

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a>SINK_ENTRY_EX и SINK_ENTRY_EX_P

Объявляет функцию обработчика *(fn*) для указанного события *(dispid),* интерфейса отправки *(iid),* для управления, идентифицированного *id.*

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентифицирует элемент управления.

*Iid*<br/>
(в) Идентифицирует интерфейс диспетчерской службы.

*пиид*<br/>
(в) Указатель на интерфейс отправки.

*Dispid*<br/>
(в) Определяет указанное событие.

*Fn*<br/>
(в) Название функции обработчика событий. Эта функция должна `_stdcall` использовать вызываемую конвенцию и иметь соответствующую подпись в стиле dispinterface.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>Remarks

Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a>SINK_ENTRY_INFO и SINK_ENTRY_INFO_P

Используйте SINK_ENTRY_INFO макрос в карте раковины события, чтобы предоставить информацию, необходимую [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) для маршрутизации к соответствующей функции обработчика.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Неподписанный беспредел, идентифицирующий источник события. Это значение должно соответствовать параметру шаблона *nID,* используемому в соответствующем базовом классе [IDispEventSimpleImpl.](../../atl/reference/idispeventsimpleimpl-class.md)

*Iid*<br/>
(в) IID, который идентифицирует интерфейс диспетчерской службы.

*пиид*<br/>
(в) Указатель на IID, который идентифицирует интерфейс диспетчерской службы.

*Dispid*<br/>
(в) DISPID идентифицирует указанное событие.

*Fn*<br/>
(в) Название функции обработчика событий. Эта функция должна `_stdcall` использовать вызываемую конвенцию и иметь соответствующую подпись в стиле dispinterface.

*info*<br/>
(в) Введите информацию для функции обработчика событий. Информация этого типа предоставляется в виде `_ATL_FUNC_INFO` указателя на структуру. CC_CDECL является единственным вариантом, поддерживаемым в Windows `_ATL_FUNC_INFO` CE для поля CALLCONV структуры. Любое другое значение не поддерживается, таким образом, его поведение неопределенно.

### <a name="remarks"></a>Remarks

Первые четыре макропараметра такие же, как и для [SINK_ENTRY_EX](#sink_entry_ex) макроса. Окончательный параметр предоставляет информацию о типе события. Ce ATL реализация sinks событий ActiveX поддерживает только значения возврата типа HRESULT или недействительными из ваших методов обработчика событий; любое другое значение возврата не поддерживается, и его поведение не определено.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[Композитные контрольные глобальные функции](../../atl/reference/composite-control-global-functions.md)
