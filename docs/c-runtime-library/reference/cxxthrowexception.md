---
title: _CxxThrowException
ms.date: 11/04/2016
api_name:
- _CxxThrowException
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: a5b614d25502ddd5a58aedcf2ec843b2b1ab9d47
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942043"
---
# <a name="_cxxthrowexception"></a>_CxxThrowException

Создает запись об исключении и вызывает среду выполнения для запуска обработки исключения.

## <a name="syntax"></a>Синтаксис

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>Параметры

*пексцептионобжект*<br/>
Получает объект, который создал событие.

*псровинфо*<br/>
Сведения, необходимые для обработки исключения.

## <a name="remarks"></a>Примечания

Этот метод включается только в файл компилятора, который используется компилятором для обработки исключений. Не вызывайте этот метод напрямую из кода.

## <a name="requirements"></a>Требования

**Источника** Throw. cpp

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
