---
title: _CxxThrowException
ms.date: 11/04/2016
apiname:
- _CxxThrowException
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: 925b72a120b31029b76fa38bee73eea003511cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550337"
---
# <a name="cxxthrowexception"></a>_CxxThrowException

Создает запись об исключении и вызывает среду выполнения для запуска обработки исключения.

## <a name="syntax"></a>Синтаксис

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>Параметры

*pExceptionObject*<br/>
Получает объект, который создал событие.

*pThrowInfo*<br/>
Сведения, необходимые для обработки исключения.

## <a name="remarks"></a>Примечания

Этот метод включается только в файл компилятора, который используется компилятором для обработки исключений. Не вызывайте этот метод напрямую из кода.

## <a name="requirements"></a>Требования

**Источник:** Throw.cpp

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
