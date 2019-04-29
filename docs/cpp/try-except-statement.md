---
title: Оператор try-except
ms.date: 10/09/2018
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- _except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: 400c831eec1c570f26dfc010b4e4c61e7d21b1c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266846"
---
# <a name="try-except-statement"></a>Оператор try-except

**Блок, относящийся только к системам Microsoft**

**Try-except** инструкция является расширением Microsoft для C и C++ языков, поддерживаемых структурированная обработка исключений.

## <a name="syntax"></a>Синтаксис

> **\_\_Попробуйте**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;защищенный код<br/>
> }<br/>
> **\_\_за исключением** ( *выражение* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;код обработчика исключений<br/>
> }<br/>

## <a name="remarks"></a>Примечания

**Try-except** инструкция является расширением Microsoft для C и языков C++, которое позволяет целевым приложениям получать управление при возникновении событий, обычно завершающих выполнение программы. Такие события вызываются *исключения*, и механизм, который обрабатывает исключения вызывается *структурированная обработка исключений* (SEH).

Дополнительные сведения см. в разделе [оператор try-finally](../cpp/try-finally-statement.md).

Исключения могут быть аппаратными или программными. Даже если работа приложения после таких исключений и не может полностью восстановиться, структурированная обработка исключений позволяет отобразить информацию об ошибке и зафиксировать внутреннее состояние приложения, чтобы выполнить диагностику проблемы. Это особенно полезно для нерегулярно встречающихся неполадок, которые сложно воспроизвести.

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Однако она не предназначена специально для C++. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. Для программ на языке C++ рекомендуется использовать механизм обработки исключений C++ ([try, catch и throw](../cpp/try-throw-and-catch-statements-cpp.md) инструкций).

Составной оператор после **__try** предложение — это текст или защищенного раздела. Составной оператор после **__except** предложение является обработчиком исключения. Он задает набор действий, выполняемых при возникновении исключения в теле защищенного раздела. Выполнение происходит следующим образом:

1. Сначала выполняется защищенный раздел.

1. Если исключение не возникает во время выполнения защищенного раздела, выполнение продолжается с оператора после **__except** предложение.

1. Если исключение возникает во время выполнения защищенного раздела или в любой процедуре вызывает защищенного раздела, **__except** *выражение* (вызывается *фильтра* выражение) вычисляется и значение определяет способ обработки исключения. Есть три возможных значения:

   - EXCEPTION_CONTINUE_EXECUTION (-1) Exception is dismissed. Выполнение продолжается в точке, в которой возникло исключение.

   - EXCEPTION_CONTINUE_SEARCH (0) исключение не распознано. Программа переходит к поиску обработчика в стеке (сначала находятся выражения с оператором **try-except**, а затем обработчики со следующим наивысшим приоритетом).

   - EXCEPTION_EXECUTE_HANDLER (1) исключение распознано. Передачи управления обработчик исключений, выполнив **__except** составного оператора, а затем продолжить выполнение после **__except** блока.

Так как **__except** выражение вычисляется как выражение C, это только одно значение, оператор условного выражения или оператор "запятая". Если требуется более сложная обработка, выражение может вызывать процедуру, которая возвращает одно из этих трех значений.

Каждое приложение может иметь свой собственный обработчик исключений.

Не допускается для перехода в **__try** инструкции, но допускается выход из него. Обработчик исключений не вызывается, если процесс был завершен во время выполнения **try-except** инструкции.

Для совместимости с предыдущими версиями **_try**, **_except**, и **_leave** являются синонимами для **__try**, **__except** , и **__leave** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указан.

### <a name="the-leave-keyword"></a>Ключевое слово __leave

**__Leave** ключевое слово может использоваться только в пределах защищенного раздела оператора **попробуйте — за исключением** инструкции и его влияние — переход в конец защищенного раздела. Выполнение продолжается с первого оператора, следующего за обработчиком исключений.

Объект **goto** оператор также может переходить из защищенного раздела, и он не снижает производительность, как это делается при **try-finally** инструкции поскольку очистки стека не выполняется. Тем не менее, мы рекомендуем использовать **__leave** ключевое слово, а не **goto** инструкции так, как вы являетесь снижает вероятность ошибки при больших или сложных защищенного раздела.

### <a name="structured-exception-handling-intrinsic-functions"></a>Встроенные функции структурированной обработки исключений

Структурированная обработка исключений имеет две встроенных функции, которые можно использовать с **попробуйте — за исключением** инструкции: `GetExceptionCode` и `GetExceptionInformation`.

`GetExceptionCode` Возвращает код исключения (32-разрядное целое).

Встроенная функция `GetExceptionInformation` возвращает указатель на структуру, содержащую Дополнительные сведения об исключении. Через этот указатель можно обращаться к состоянию компьютера, которое существовало в момент возникновения аппаратного исключения. Эта структура выглядит следующим образом:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

Типы указателей `PEXCEPTION_RECORD` и `PCONTEXT` определены во включаемом файле \<winnt.h >, и `_EXCEPTION_RECORD` и `_CONTEXT` определены во включаемом файле \<excpt.h >

Можно использовать `GetExceptionCode` в обработчике исключений. Тем не менее, можно использовать `GetExceptionInformation` только в выражении фильтра исключений. Обычно она указывает на сведения, которые хранятся в стеке и уже недоступны в тот момент, когда управление передаются обработчику исключений.

Встроенная функция `AbnormalTermination` доступна в обработчике завершения. Возвращает 0, если тело **try-finally** инструкция завершается последовательным выполнением. В остальных случаях функция возвращает 1.

excpt.h определены альтернативные имена этих встроенных функций:

`GetExceptionCode` эквивалентно `_exception_code`

`GetExceptionInformation` эквивалентно `_exception_info`

`AbnormalTermination` эквивалентно `_abnormal_termination`

## <a name="example"></a>Пример

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>Вывод

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
