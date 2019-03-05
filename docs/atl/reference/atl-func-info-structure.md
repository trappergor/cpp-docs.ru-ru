---
title: Структура _ATL_FUNC_INFO
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: f6cf32bab86d741f3b0750c150c7bbc647b27ddc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299547"
---
# <a name="atlfuncinfo-structure"></a>Структура _ATL_FUNC_INFO

Содержит сведения о типе, используемые для описания метода или свойства на disp-интерфейсом.

## <a name="syntax"></a>Синтаксис

```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Участники

`cc`<br/>
Соглашение о вызовах. При использовании эту структуру с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класса, этот элемент должен быть CC_STDCALL. `CC_CDECL` только этот параметр поддерживается в Windows CE для `CALLCONV` поле `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.

`vtReturn`<br/>
Тип variant функции возвращают значение.

`nParams`<br/>
Число параметров функции.

`pVarTypes`<br/>
Массив variant типы параметров функции.

## <a name="remarks"></a>Примечания

На внутреннем уровне ATL использует эту структуру для хранения информации, полученной из библиотеки типов. Может потребоваться управлять эта структура напрямую в том случае, если предоставить сведения о типе для обработчика событий, используемый с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класс и [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) макрос.

## <a name="example"></a>Пример

Получает метод disp-интерфейса, определенных в IDL:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

необходимо определить `_ATL_FUNC_INFO` структуры:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Требования

Header: atlcom.h

## <a name="see-also"></a>См. также

[Классы и структуры](../../atl/reference/atl-classes.md)<br/>
[Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
