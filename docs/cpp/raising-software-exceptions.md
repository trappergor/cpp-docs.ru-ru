---
title: Создание программных исключений
ms.date: 11/04/2016
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
ms.openlocfilehash: 7c58ae2e2b6635345a162d11d2b75a9865d37751
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246407"
---
# <a name="raising-software-exceptions"></a>Создание программных исключений

Некоторые из самых распространенных источников ошибок программы не отмечены системой как исключения. Например, при попытке выделить блок памяти при недостаточной памяти среда выполнения или функция API не создает исключение, но возвращает код ошибки.

However, you can treat any condition as an exception by detecting that condition in your code and then reporting it by calling the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function. Отмечая ошибки таким образом, можно использовать преимущества структурированной обработки исключений в любом типе ошибки времени выполнения.

Чтобы использовать структурированную обработку исключений с ошибками, выполните следующие действия.

- Определите собственный код исключения для события.

- Call `RaiseException` when you detect a problem.

- Используйте фильтры обработки исключений для проверки определенного кода исключения.

The \<winerror.h> file shows the format for exception codes. Чтобы проверить, что определяемый код не будет конфликтовать с существующим кодом исключения, задайте для третьего наиболее значимого бита значение 1. Следует установить четыре наиболее значимых бита, как показано в следующей таблице.

|Bits|Рекомендуемый двоичный параметр|Описание|
|----------|--------------------------------|-----------------|
|31-30|11|Эти два бита описываются основное состояние кода: 11 = ошибка, 00 = успех, 01 = информация, 10 = предупреждение.|
|29|1|Бит клиента. Установите значение 1 для пользовательских кодов.|
|28|0|Зарезервированный бит. (Оставьте значение 0.)|

При желании для первых двух битов можно задать параметр, отличный от двоичного параметра 11, хотя параметр "ошибка" подходит для большинства исключений. Помните, что биты 29 и 28 следует установить так, как показано в предыдущей таблице.

The resulting error code should therefore have the highest four bits set to hexadecimal E. For example, the following definitions define exception codes that do not conflict with any Windows exception codes. (Хотя может потребоваться проверить, какие коды используются сторонними библиотеками DLL.)

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

После определения кода исключения его можно использовать для создания исключения. For example, the following code raises the `STATUS_INSUFFICIENT_MEM` exception in response to a memory allocation problem:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

Если требуется просто создать исключение, можно установить для трех последних параметров значение 0. Три последних параметра полезны при передаче дополнительной информации и установке флага, который запрещает обработчикам продолжать выполнение. See the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function in the Windows SDK for more information.

Затем можно проверить определенные коды в фильтрах обработки исключений. Пример:

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>См. также

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Structured exception handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)