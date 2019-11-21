---
title: Structured Exception Handling (C/C++)
ms.date: 08/14/2018
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 942a7e48e4315454476bfe93c68169f461b006b2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245129"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

Structured exception handling (SEH) is a Microsoft extension to C to handle certain exceptional code situations, such as hardware faults, gracefully. Although Windows and Microsoft C++ support SEH, we recommend that you use ISO-standard C++ exception handling because it makes your code more portable and flexible. Nevertheless, to maintain existing code or for particular kinds of programs, you still might have to use SEH.

**Microsoft specific:**

## <a name="grammar"></a>Грамматика

*try-except-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__finally** *compound-statement*

## <a name="remarks"></a>Заметки

With SEH, you can ensure that resources such as memory blocks and files are released correctly if execution unexpectedly terminates. You can also handle specific problems—for example, insufficient memory—by using concise structured code that does not rely on **goto** statements or elaborate testing of return codes.

Операторы try-except и try-finally, которые упоминаются в этом разделе, являются расширениями языка C для систем Microsoft. Они поддерживают SEH, позволяя приложениям получать контроль над программой после событий, которые в иных ситуациях привели бы к завершению выполнения. Хотя обработка ошибок SEH работает с исходными файлами C++, она не была создана специально для этого языка. If you use SEH in a C++ program that you compile by using the [/EHa or /EHsc](../build/reference/eh-exception-handling-model.md) option, destructors for local objects are called but other execution behavior might not be what you expect. For an illustration, see the example later in this article. In most cases, instead of SEH we recommend that you use ISO-standard [C++ exception handling](../cpp/try-throw-and-catch-statements-cpp.md), which the Microsoft C++ compiler also supports. С помощью обработки исключений C++ можно повысить переносимость кода и обрабатывать исключения любого типа.

If you have C code that uses SEH, you can mix it with C++ code that uses C++ exception handling. For information, see [Handle structured exceptions in C++](../cpp/exception-handling-differences.md).

Существует два механизма SEH.

- [Exception handlers](../cpp/writing-an-exception-handler.md), or **__except** blocks, which can respond to or dismiss the exception.

- [Termination handlers](../cpp/writing-a-termination-handler.md), or **__finally** blocks, which are always called, whether an exception causes termination or not.

Эти два типа обработчиков различаются, однако тесно взаимодействию в процессе, который называется "развертыванием стека". When a structured exception occurs, Windows looks for the most recently installed exception handler that is currently active. Обработчик может выполнить одно из трех действий:

- не распознать исключение и передать управление другим обработчикам;

- распознать исключение, но отбросить его;

- распознать исключение и обработать его.

Обработчик исключений, распознавший исключение, может находиться за пределами функции, которая выполнялась, когда возникло исключение. В некоторых случаях он может находиться в функции, хранящейся гораздо выше по стеку. Выполняемая в настоящее время функция и все прочие функции в кадре стека завершаются. During this process, the stack is "unwound;" that is, local non-static variables of terminated functions are cleared from the stack.

По мере развертывания стека операционная система вызывает все обработчики завершения, которые были написаны для каждой функции. При помощи обработчиков завершения можно освободить ресурсы, которые в противном случае оставались бы открытыми ненормального завершения. If you've entered a critical section, you can exit it in the termination handler. Если ожидается завершение программы, можно выполнить другие задачи обслуживания, например закрыть и удалить временные файлы.

## <a name="next-steps"></a>Следующие шаги

- [Writing an exception handler](../cpp/writing-an-exception-handler.md)

- [Writing a termination handler](../cpp/writing-a-termination-handler.md)

- [Обработка структурированных исключений в C++](../cpp/exception-handling-differences.md)

## <a name="example"></a>Пример

As stated earlier, destructors for local objects are called if you use SEH in a C++ program and compile it by using the **/EHa** or **/EHsc** option. Однако если при этом используются исключения C++, то поведение во время выполнения может отличаться от ожидаемого. This example demonstrates these behavioral differences.

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

If you use **/EHsc** to compile this code but the local test control macro `CPPEX` is undefined, there is no execution of the `TestClass` destructor and the output looks like this:

```Output
Triggering SEH exception
Executing SEH __except block
```

If you use **/EHsc** to compile the code and `CPPEX` is defined by using `/DCPPEX` (so that a C++ exception is thrown), the `TestClass` destructor executes and the output looks like this:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

If you use **/EHa** to compile the code, the `TestClass` destructor executes regardless of whether the exception was thrown by using `std::throw` or by using SEH to trigger the exception, that is, whether `CPPEX` defined or not. Вывод выглядит следующим образом.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Дополнительные сведения см. в статье [/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[Errors and Exception Handling](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Structured Exception Handling (Windows)](/windows/win32/debug/structured-exception-handling)
