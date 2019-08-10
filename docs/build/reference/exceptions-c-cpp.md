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
ms.openlocfilehash: cf38af464f08e143ed9073befe30f6aeb8b913b6
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915460"
---
# <a name="exceptions-cc"></a>Исключения (C/C++)

При обнаружении сбоев могут возникать два кода исключений:

- Для сбоя **LoadLibrary**

- Для ошибки **GetProcAddress**

Ниже приведены сведения об исключении:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Вызываемые коды исключений — это стандартные значения Вкппексцептион (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) и Вкппексцептион (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). Исключение передает указатель на структуру **делайлоадинфо** в значении лпдворд, которое может быть извлечено **жетексцептионинформатион** в поле структура [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-exception_record) , матрице ExceptionInformation [0].

Кроме того, если в поле Граттрс заданы неверные биты, выдается исключение ERROR_INVALID_PARAMETER. Это исключение для всех целей и назначений, неустранимое.

Дополнительные сведения см. в разделе [определения структур и констант](structure-and-constant-definitions.md) .

## <a name="see-also"></a>См. также

[Обработка ошибок и предупреждений](error-handling-and-notification.md)
