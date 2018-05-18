---
title: Структура _ATL_FUNC_INFO | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa81e83d353c542ea5b2b6e8e5e8fe32f7c57606
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="atlfuncinfo-structure"></a>Структура _ATL_FUNC_INFO
Содержит сведения о типе, используемый для описания метода или свойства на disp-интерфейса.  
  
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
 **cc**  
 Соглашение о вызовах. При использовании этой структуры с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класса, этот член должен быть **CC_STDCALL**. `CC_CDECL` единственный параметр, который поддерживается в Windows CE для `CALLCONV` поле `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.  
  
 **vtReturn**  
 Тип variant функции возвращают значение.  
  
 **nParams**  
 Количество параметров функции.  
  
 **pVarTypes**  
 Массив типов variant параметров функции.  
  
## <a name="remarks"></a>Примечания  
 На внутреннем уровне ATL использует следующую структуру для хранения информации, полученной из библиотеки типов. Может потребоваться напрямую управлять этой структуры, если предоставить сведения о типе для обработчика событий, используемые с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класса и [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) макрос.  
  
## <a name="example"></a>Пример  
 Заданный метод disp-интерфейса, определенных в IDL:  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 При определении `_ATL_FUNC_INFO` структуры:  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
## <a name="see-also"></a>См. также  
  [Классы и структуры](../../atl/reference/atl-classes.md)  
 [Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





