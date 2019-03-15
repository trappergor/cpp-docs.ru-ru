---
title: Исключения (C/C++)
ms.date: 11/04/2016
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: f80b99943b103dcf90c05d59df3169e0e05d79f4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811671"
---
# <a name="exceptions-cc"></a>Исключения (C/C++)

Два кода исключения могут возникать при возникновении ошибок:

- Для **LoadLibrary** сбоя

- Для **GetProcAddress** сбоя

Вот сведения об исключении:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Исключение кодами исключений — это стандартный VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) и значения VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Исключение передает указатель на **DelayLoadInfo** структуры в значении LPDWORD, можно получить с **GetExceptionInformation** в [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record) Структура, поле ExceptionInformation [0].

Кроме того Если в поле grAttrs неверные биты, ERROR_INVALID_PARAMETER исключение. Это исключение, для всех, Собрав Неустранимая.

См. в разделе [определение структуры и константы](structure-and-constant-definitions.md) Дополнительные сведения.

## <a name="see-also"></a>См. также

[Обработка ошибок и предупреждений](error-handling-and-notification.md)
