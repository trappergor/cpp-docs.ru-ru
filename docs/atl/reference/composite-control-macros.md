---
title: "Макросы в составной элемент управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 9fb8a907c8052c9816d6b87247e903a63f34a5be
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-macros"></a>Макросы в составной элемент управления
Эти макросы определение схемы приемников событий и записи.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Отмечает начало картой приемника событий для составного элемента управления.|  
|[END_SINK_MAP](#end_sink_map)|Отмечает конец картой приемника событий для составного элемента управления.|  
|[SINK_ENTRY](#sink_entry)|Запись, которую картой приемника событий.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Запись, которую картой приемника событий содержит дополнительный параметр.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017 г.) Аналогично SINK_ENTRY_EX, за исключением того, что он принимает указатель на идентификатор iid.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Запись картой приемника событий вручную предоставленного сведения о типе для использования с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017 г.) Аналогично SINK_ENTRY_INFO, за исключением того, что он принимает указатель на идентификатор iid.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  

##  <a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 Объявляет начало картой приемника событий для составного элемента управления.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Определяет элемент управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="end_sink_map"></a>END_SINK_MAP  
 Объявляет конец картой приемника событий для составного элемента управления.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry"></a>SINK_ENTRY  
 Объявляет функцию-обработчик ( `fn`) для указанного события ( `dispid`), определяемый элемента управления `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентифицирует элемент управления.  
  
 `dispid`  
 [in] Определяет указанное событие.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейс в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_ex"></a>SINK_ENTRY_EX и SINK_ENTRY_EX_P
 Объявляет функцию-обработчик ( `fn`) для указанного события ( `dispid`), интерфейс диспетчеризации ( *iid)*, для элемента управления, идентифицируемый `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентифицирует элемент управления.  
  
 `iid`  
 [in] Определяет интерфейс диспетчеризации.  

 `piid`  
 [in] Указатель на интерфейс диспетчеризации.  
  
 `dispid`  
 [in] Определяет указанное событие.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейс в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#136;](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_info"></a>SINK_ENTRY_INFO и SINK_ENTRY_INFO_P  
 Используйте `SINK_ENTRY_INFO` макрос в картой приемника событий, чтобы предоставить сведения, необходимые для [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) направляет функция соответствующего обработчика события.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Целое число без знака, определение источника события. Это значение должно соответствовать `nID` параметр шаблона, используемый в связанных [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) базового класса.  
  
 `iid`  
 [in] Идентификатор IID, определяющий интерфейс диспетчеризации.  

 `piid`  
 [in] Указатель на идентификатор IID, определяющий интерфейс диспетчеризации.
  
 `dispid`  
 [in] Идентификатор DISPID определение указанного события.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейс в стиле.  
  
 `info`  
 [in] Введите сведения о функции обработчика событий. Тип сведения предоставляются в виде указателя `_ATL_FUNC_INFO` структуры. `CC_CDECL`только этот параметр поддерживается в Windows CE для `CALLCONV` поле `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.  
  
### <a name="remarks"></a>Примечания  
 Параметры макроса первые четыре совпадают, такие как [SINK_ENTRY_EX](#sink_entry_ex) макрос. Последний параметр предоставляет сведения о типе для события. Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  

## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции составного элемента управления](../../atl/reference/composite-control-global-functions.md)

