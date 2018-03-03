---
title: "Макросы составного элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b609801a1716e47b208644be02d4746abf8c288a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="composite-control-macros"></a>Макросы составного элемента управления
Эти макросы определяют схемы приемников событий и записи.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Отмечает начало карты приемник событий для составного элемента управления.|  
|[END_SINK_MAP](#end_sink_map)|Отмечает конец карты приемник событий для составного элемента управления.|  
|[SINK_ENTRY](#sink_entry)|Запись в схеме событий приемника.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Запись для карты приемник событий с дополнительным параметром.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017 г.) Аналогично SINK_ENTRY_EX, за исключением того, что он принимает указатель на iid.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Запись в схеме приемника событий вручную предоставленного сведения о типе для использования с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017 г.) Аналогично SINK_ENTRY_INFO, за исключением того, что он принимает указатель на iid.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  

##  <a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 Объявляет начало схеме приемника событий для составного элемента управления.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Определяет элемент управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="end_sink_map"></a>END_SINK_MAP  
 Объявляет конец карты приемник событий для составного элемента управления.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry"></a>SINK_ENTRY  
 Объявляет функцию-обработчик ( `fn`) для указанного события ( `dispid`), определяемый элемента управления `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Определяет элемент управления.  
  
 `dispid`  
 [in] Определяет указанное событие.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эта функция должна использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейса в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_ex"></a>SINK_ENTRY_EX и SINK_ENTRY_EX_P
 Объявляет функцию-обработчик ( `fn`) для указанного события ( `dispid`), интерфейса диспетчеризации ( *iid)*, для элемента управления, определяется `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Определяет элемент управления.  
  
 `iid`  
 [in] Определяет интерфейс диспетчеризации.  

 `piid`  
 [in] Указатель на интерфейс диспетчеризации.  
  
 `dispid`  
 [in] Определяет указанное событие.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эта функция должна использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейса в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_info"></a>SINK_ENTRY_INFO и SINK_ENTRY_INFO_P  
 Используйте `SINK_ENTRY_INFO` макрос в картой приемника событий, чтобы предоставить информацию, необходимую для [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) направляет функция соответствующего обработчика события.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Целое число без знака, определение источника событий. Это значение должно соответствовать `nID` параметр шаблона, используемый в связанном [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) базового класса.  
  
 `iid`  
 [in] Идентификатор IID, определяющий интерфейс диспетчеризации.  

 `piid`  
 [in] Указатель на IID, определяющий интерфейс диспетчеризации.
  
 `dispid`  
 [in] Идентификатор DISPID, определение указанного события.  
  
 `fn`  
 [in] Имя функции обработчика событий. Эта функция должна использовать **_stdcall** соглашение о вызовах и иметь сигнатуру, соответствующие disp-интерфейса в стиле.  
  
 `info`  
 [in] Введите сведения о функции обработчика событий. Тип сведения предоставляются в виде указателя `_ATL_FUNC_INFO` структуры. `CC_CDECL`единственный параметр, который поддерживается в Windows CE для `CALLCONV` поле `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.  
  
### <a name="remarks"></a>Примечания  
 Первые четыре макропараметров совпадают, такие как [SINK_ENTRY_EX](#sink_entry_ex) макрос. Последний параметр предоставляет сведения о типе для события. Реализация CE ATL ActiveX событий приемники только поддерживает возврат значения типа HRESULT или void из вашего методы обработчиков событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  

## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции составных элементов управления](../../atl/reference/composite-control-global-functions.md)
