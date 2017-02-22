---
title: "_ATL_FUNC_INFO Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_FUNC_INFO"
  - "ATL::_ATL_FUNC_INFO"
  - "ATL._ATL_FUNC_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_FUNC_INFO structure"
  - "ATL_FUNC_INFO structure"
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# _ATL_FUNC_INFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Содержит сведения о типе, используемая для описания метод или свойство в диспетчерский интерфейс.  
  
## Синтаксис  
  
```  
  
      struct _ATL_FUNC_INFO{  
   CALLCONV cc;  
   VARTYPE vtReturn;  
   SHORT nParams;  
   VARTYPE pVarTypes[_ATL_MAX_VARTYPES];  
};  
```  
  
## Члены  
 **cc**  
 Соглашение о вызовах.  При использовании этой структуры с классом [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), этот элемент должен быть **CC\_STDCALL**.  `CC_CDECL` единственный параметр поддерживается в Windows CE для поля `CALLCONV` структуры `_ATL_FUNC_INFO`.  Любое другое значение не поддерживается, таким образом, его неназначенной реакцией на событие.  
  
 **vtReturn**  
 Другой тип возвращаемого значения функции.  
  
 **nParams**  
 Число параметров функции.  
  
 **pVarTypes**  
 Массив различных типах параметров функции.  
  
## Заметки  
 Внутри библиотеки ATL использует эту структуру для хранения сведений, полученный из библиотеки типов.  Эту структуру можно управлять непосредственно если указать сведения о типе для используемого обработчика событий с классом [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) и макросом [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md).  
  
## Пример  
 Данный метод диспетчерский интерфейс, указанный в IDL.  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/CPP/atl-func-info-structure_1.idl)]  
  
 вы определили бы структуру `_ATL_FUNC_INFO`:  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/CPP/atl-func-info-structure_2.h)]  
  
## Требования  
 **Header:** atlcom.h  
  
## См. также  
 [Структуры](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)