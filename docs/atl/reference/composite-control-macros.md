---
title: Макросы составного элемента управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c28ab24323f4636ede4ad7e9cccbdb2ceceac71d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879826"
---
# <a name="composite-control-macros"></a>Макросы составного элемента управления
Эти макросы определяют схемы приемников событий и записи.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Отмечает начало карты приемника событий для составного элемента управления.|  
|[END_SINK_MAP](#end_sink_map)|Помечает конец карты приемника событий для составного элемента управления.|  
|[SINK_ENTRY](#sink_entry)|Запись для карты приемника событий.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Запись для карты приемника событий с дополнительным параметром.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017 г.) Аналогичен SINK_ENTRY_EX, за исключением того, что он принимает указатель на iid.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Запись к схеме событий приемника данными вручную указанного типа для использования с [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017 г.) Аналогичен SINK_ENTRY_INFO, за исключением того, что он принимает указатель на iid.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP  
 Объявляет начало карты приемника событий для составного элемента управления.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Параметры  
 *_класса*  
 [in] Определяет элемент управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="end_sink_map"></a>  END_SINK_MAP  
 Объявляет конец карты приемника событий для составного элемента управления.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry"></a>  SINK_ENTRY  
 Объявляет функцию-обработчик (*fn*) для указанного события (*dispid*), элемента управления, идентифицируемый *идентификатор*.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Определяет элемент управления.  
  
 *Идентификатор DISPID*  
 [in] Определяет указанное событие.  
  
 *fn*  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать `_stdcall` соглашение о вызовах и иметь сигнатуру, соответствующую disp-интерфейс в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX и SINK_ENTRY_EX_P
 Объявляет функцию-обработчик (*fn*) для указанного события (*dispid*), интерфейса диспетчеризации (*iid*), для управления, идентифицируемого *идентификатор*.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Определяет элемент управления.  
  
 *IID*  
 [in] Определяет интерфейс диспетчеризации.  

 *piid*  
 [in] Указатель на интерфейс диспетчеризации.  
  
 *Идентификатор DISPID*  
 [in] Определяет указанное событие.  
  
 *fn*  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать `_stdcall` соглашение о вызовах и иметь сигнатуру, соответствующую disp-интерфейс в стиле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Примечания  
 Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  
##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO и SINK_ENTRY_INFO_P  
 Используйте макрос SINK_ENTRY_INFO в картой приемника событий для предоставления сведений, необходимых для [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) маршрутизацию событий в функцию соответствующему обработчику.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Целое число без знака, определяющий источник событий. Это значение должно соответствовать *nID* параметр шаблона, используемый в связанном [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) базового класса.  
  
 *IID*  
 [in] Идентификатор IID, определяющий интерфейс диспетчеризации.  

 *piid*  
 [in] Указатель на IID, определяющий интерфейс диспетчеризации.
  
 *Идентификатор DISPID*  
 [in] Идентификатор DISPID, определение указанного события.  
  
 *fn*  
 [in] Имя функции обработчика событий. Эту функцию необходимо использовать `_stdcall` соглашение о вызовах и иметь сигнатуру, соответствующую disp-интерфейс в стиле.  
  
 *Сведения о*  
 [in] Сведения о типе для функция обработчика событий. Эти сведения о типах предоставляется в виде указателя на `_ATL_FUNC_INFO` структуры. CC_CDECL является единственным параметром, поддерживаемые в Windows CE для поля CALLCONV `_ATL_FUNC_INFO` структуры. Любое другое значение не поддерживается таким образом его поведение не определено.  
  
### <a name="remarks"></a>Примечания  
 Параметры первые четыре макроса — такие же, как для [SINK_ENTRY_EX](#sink_entry_ex) макрос. Последний параметр предоставляет сведения о типе для события. Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.  
  

## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции составных элементов управления](../../atl/reference/composite-control-global-functions.md)
