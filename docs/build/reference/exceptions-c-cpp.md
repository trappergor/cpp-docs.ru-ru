---
title: "Исключения (C/C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs:
- C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 635e2b1406e9919425a396b6f49fe8eb6efd81eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-cc"></a>Исключения (C/C++)
Два кода исключения могут возникать при возникновении ошибок:  
  
-   Для **LoadLibrary** сбоя  
  
-   Для **GetProcAddress** сбоя  
  
 Вот сведения об исключении:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Коды исключений, который создается — это стандартная VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) и значения VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Исключение передается указатель **DelayLoadInfo** структуры в значении LPDWORD, можно получить с **GetExceptionInformation** в [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) Структура поля ExceptionInformation [0].  
  
 Кроме того Если в поле grAttrs заданы неверные bits, ERROR_INVALID_PARAMETER исключение. Это исключение, в качестве исчезнувшим, Неустранимая.  
  
 В разделе [определение структуры и константы](../../build/reference/structure-and-constant-definitions.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)