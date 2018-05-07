---
title: Исключения (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 819f9424b2439cc49517afe54d62a8ed4f06d22d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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