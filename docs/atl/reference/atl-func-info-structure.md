---
title: "Структура _ATL_FUNC_INFO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c18e1c5a41ef910cfe327fdbdd8d8885ef30a092
ms.lasthandoff: 02/24/2017

---
# <a name="atlfuncinfo-structure"></a>Структура _ATL_FUNC_INFO
Содержит сведения о типе, используется для описания метода или свойства на disp-интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>Члены  
 **копия**  
 Соглашение о вызовах. При использовании этой структуры с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класса, этот член должен быть **CC_STDCALL**. `CC_CDECL`только этот параметр поддерживается в Windows CE для `CALLCONV` поле `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.  
  
 **vtReturn**  
 Тип variant, функции возвращают значение.  
  
 **nParams**  
 Количество параметров функции.  
  
 **pVarTypes**  
 Массив типов variant параметров функции.  
  
## <a name="remarks"></a>Примечания  
 На внутреннем уровне ATL использует эту структуру для хранения информации, полученной из библиотеки типов. Может потребоваться для управления этой структуры напрямую, если предоставить сведения о типе для обработчика событий, используемые с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) класса и [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) макрос.  
  
## <a name="example"></a>Пример  
 Получает метод disp-интерфейса, определенных в IDL:  
  
 [!code-cpp[NVC_ATL_Windowing&#139;](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 При определении `_ATL_FUNC_INFO` структуры:  
  
 [!code-cpp[NVC_ATL_Windowing&#140;](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)   
 [Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)






