---
title: "Debugging and Error Reporting Global Functions | Microsoft Docs"
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
  - "функции [ATL], сообщения об ошибках"
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Debugging and Error Reporting Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти функции предоставляют полезный отладке и функции трассировки.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|Возвращает код ошибки `GetLastError` в форме HRESULT.|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Преобразует код ошибки Win32 в HRESULT.|  
|[AtlReportError](../Topic/AtlReportError.md)|Настройка **IErrorInfo** для предоставления сведений об ошибке клиента.|  
|[AtlThrow](../Topic/AtlThrow.md)|Создает исключение `CAtlException`.|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Эта функция вызывается для обозначения ошибки на основе результата функции Windows `GetLastError`.|  
|[AtlTraceLoadSettings](../../misc/atltraceloadsettings.md)|Эта функция вызывается, чтобы загрузить параметры трассировки из файла.|  
|[AtlTraceSaveSettings](../../misc/atltracesavesettings.md)|Эта функция вызывается, чтобы сохранить текущие параметры трассировки в файл.|  
  
## См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Debugging and Error Reporting Macros](../../atl/reference/debugging-and-error-reporting-macros.md)