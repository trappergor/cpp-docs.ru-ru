---
title: "Исключения (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ERROR_MOD_NOT_FOUND"
  - "vcppException"
  - "ERROR_SEVERITY_ERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++, отложенная загрузка библиотек DLL"
  - "отложенная загрузка библиотек DLL, исключения"
  - "ERROR_MOD_NOT_FOUND - исключение"
  - "ERROR_SEVERITY_ERROR - исключение"
  - "vcppException"
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Исключения (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При возникновении ошибок могут создаваться два кода исключения:  
  
-   Для ошибок **LoadLibrary**;  
  
-   Для ошибок **GetProcAddress**.  
  
 Вот сведения об исключениях:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Коды создаваемых исключений — это стандартные значения VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_MOD\_NOT\_FOUND\) и VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_PROC\_NOT\_FOUND\).  Исключение содержит указатель на структуру **DelayLoadInfo** в значении типа LPDWORD, которое может быть считано с помощью функции **GetExceptionInformation** в структуре [EXCEPTION\_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) в поле ExceptionInformation\[0\].  
  
 Помимо этого, если в поле grAttrs установлены неправильные биты, то возникает исключение ERROR\_INVALID\_PARAMETER.  Это исключение во всех случаях является неустранимым.  
  
 Дополнительные сведения см. в разделе [Определения структур и констант](../../build/reference/structure-and-constant-definitions.md).  
  
## См. также  
 [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)