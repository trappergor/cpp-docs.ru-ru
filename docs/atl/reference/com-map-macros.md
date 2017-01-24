---
title: "COM Map Macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы COM, COM map macros"
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM Map Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти макросы указывают сопоставления COM\-интерфейса.  
  
|||  
|-|-|  
|[BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)|Отмечает начало записей сопоставления COM\-интерфейса.|  
|[COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md)|Интерфейсы перейдет в сопоставление интерфейса модели COM.|  
|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)|Используйте этот макрос для устранения неоднозначности 2 ветвления наследования.|  
|[COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)|Используйте этот макрос, чтобы ввести интерфейс в сопоставление модели COM и задать его ИДЕНТИФИКАТОРА.|  
|[COM\_INTERFACE\_ENTRY2\_IID](../Topic/COM_INTERFACE_ENTRY2_IID.md)|То же, что и [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md), за исключением того, что можно указать другое ИДЕНТИФИКАТОРА.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)|Если интерфейс указанный `iid` запрашивается для `COM_INTERFACE_ENTRY_AGGREGATE` переадресует к `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AGGREGATE_BLIND.md)|То же, что и [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), за исключением того, что выполнение запроса для получения всех IID приводит к переадресованы запрос к `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)|То же, что и [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), за исключением если `punk`**NULL**, то он автоматически создает статистическое выражение, описанный `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)|То же, что и [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md), за исключением того, что выполнение запроса для получения всех IID приводит к переадресованы запрос к `punk`, и если `punk`**NULL**, то автоматически создать агрегат, описанный `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_BREAK](../Topic/COM_INTERFACE_ENTRY_BREAK.md)|Заставляет программу вызвать [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297), если указанный интерфейс запрашивается.|  
|[COM\_INTERFACE\_ENTRY\_CACHED\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_CACHED_TEAR_OFF.md)|Сохраняет сведения о интерфейс\- определенного для каждого экземпляра.|  
|[COM\_INTERFACE\_ENTRY\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_TEAR_OFF.md)|Предоставляет свои перемещаемые интерфейсы.|  
|[COM\_INTERFACE\_ENTRY\_CHAIN](../Topic/COM_INTERFACE_ENTRY_CHAIN.md)|Обрабатывает сопоставление модели COM базового класса при обработке достигает эту запись в сопоставлении модели COM.|  
|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)|Общий механизм циклический в `QueryInterface` библиотеки ATL логику.|  
|[COM\_INTERFACE\_ENTRY\_FUNC\_BLIND](../Topic/COM_INTERFACE_ENTRY_FUNC_BLIND.md)|То же, что и [COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md), за исключением того, что выполнение запроса для получения всех IID, приводят к вызову `func`.|  
|[COM\_INTERFACE\_ENTRY\_NOINTERFACE](../Topic/COM_INTERFACE_ENTRY_NOINTERFACE.md)|Возвращает **E\_NOINTERFACE** и заканчивается сопоставление модели COM, если указанный интерфейс запрашивается для обработки.|  
|[END\_COM\_MAP](../Topic/END_COM_MAP.md)|Помечает конец записей сопоставления COM\-интерфейса.|  
  
## См. также  
 [Macros](../../atl/reference/atl-macros.md)   
 [COM Map Global Functions](../../atl/reference/com-map-global-functions.md)