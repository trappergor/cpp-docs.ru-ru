---
title: "Debugging and Error Reporting Macros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "макросы, сообщения об ошибках"
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Debugging and Error Reporting Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти макросы предоставляют полезный отладке и функции трассировки.  
  
|||  
|-|-|  
|[\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md)|Записывает в окно вывода, все утечки интерфейса, обнаружены при `_Module.Term` вызываются.|  
|[\_ATL\_DEBUG\_QI](../Topic/_ATL_DEBUG_QI.md)|Записывает все вызовы `QueryInterface` в окно вывода.|  
|[ATLASSERT](../Topic/ATLASSERT.md)|Выполняет одну и ту же функциональность, что обнаружен макрос [\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) в библиотеке времени выполнения языка c.|  
|[ATLENSURE](../Topic/ATLENSURE.md)|Выполняет проверку параметров.  При необходимости вызовите `AtlThrow`|  
|[ATLTRACENOTIMPL](../Topic/ATLTRACENOTIMPL.md)|Отправляет сообщение в устройство резервного копирования, что указанная функция не реализована.|  
|[ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md)|Информирует предупреждений на устройство вывода, как окно отладчика, в соответствии с отображенным флагам и слоями.  Включено для обеспечения обратной совместимости.|  
|[ATLTRACE2](../Topic/ATLTRACE2.md)|Информирует предупреждений на устройство вывода, как окно отладчика, в соответствии с отображенным флагам и слоями.|  
  
## См. также  
 [Macros](../../atl/reference/atl-macros.md)   
 [Debugging and Error Reporting Global Functions](../../atl/reference/debugging-and-error-reporting-global-functions.md)