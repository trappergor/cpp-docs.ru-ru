---
title: "try-except инструкции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 240b8ad1b0cfd9c8b85b58c8d2309fb97f961573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="try-except-statement"></a>Оператор try-except

**Блок, относящийся только к системам Microsoft**  
**Try-except** является расширением Microsoft для C и C++ языков, поддерживаемых структурированной обработки исключений.  

## <a name="syntax"></a>Синтаксис  
  
> **__try**   
> {  
>    защищенный код  
> }  
> **__except** ( *выражение* )  
> {  
>    код обработчика исключений  
> }  

## <a name="remarks"></a>Примечания

**Try-except** является расширением Microsoft для C C++ языков и позволяет целевым приложениям получать управление программой при возникновении событий, обычно завершающих выполнение программы. Такие события вызываются *исключения*, а механизм, который обрабатывает исключения, называется *структурированная обработка исключений* (SEH).

Дополнительные сведения см. в разделе [оператор try-finally](../cpp/try-finally-statement.md).

Исключения могут быть аппаратными или программными. Даже если работа приложения после таких исключений и не может полностью восстановиться, структурированная обработка исключений позволяет отобразить информацию об ошибке и зафиксировать внутреннее состояние приложения, чтобы выполнить диагностику проблемы. Это особенно полезно для нерегулярно встречающихся неполадок, которые сложно воспроизвести.

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Однако она не предназначена специально для C++. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. Для программ на языке C++, рекомендуется использовать механизм обработки исключений C++ ([try, catch и throw](../cpp/try-throw-and-catch-statements-cpp.md) инструкций).

Составной оператор после предложения `__try` образует тело защищенного раздела. Составной оператор после предложения `__except` является обработчиком исключения. Он задает набор действий, выполняемых при возникновении исключения в теле защищенного раздела. Выполнение происходит следующим образом:

1. Сначала выполняется защищенный раздел.

2. Если исключение при этом не возникает, выполнение переходит в инструкцию, стоящую после предложения `__except`.  

3. Если исключение возникает во время выполнения защищенного раздела или в любой процедуре вызывает защищенного раздела, `__except` *выражение* (называется *фильтра* выражение) вычисляется и значение Определяет способ обработки исключения. Поддерживается три значения:

   **EXCEPTION_CONTINUE_EXECUTION (-1)** исключение отбрасывается. Выполнение продолжается в точке, в которой возникло исключение.

   **EXCEPTION_CONTINUE_SEARCH (0)** исключение не распознается. Программа переходит к поиску обработчика в стеке (сначала находятся выражения с оператором **try-except**, а затем обработчики со следующим наивысшим приоритетом).

   **EXCEPTION_EXECUTE_HANDLER (1)** исключение распознано. Управление передается обработчику исключений. Для этого выполняется составной оператор `__except`, а затем выполнение продолжается за блоком `__except`.

Поскольку выражение `__except` вычисляется как выражение C, оно ограничивается одиночным значением, оператором условного выражения и оператором запятой. Если требуется более сложная обработка, выражение может вызывать процедуру, которая возвращает одно из этих трех значений.

Каждое приложение может иметь свой собственный обработчик исключений.

Переходить к оператору `__try` недопустимо, но переход из него допускается. Обработчик исключений не вызывается, если процесс был завершен во время выполнения **try-except** инструкции.  
  
Дополнительные сведения см. в статье базы знаний Q315937 "Практическое руководство. Перехват переполнения стека в приложении Visual C++".  
  
## <a name="the-leave-keyword"></a>Ключевое слово __leave

`__leave` Ключевое слово может использоваться только в защищенном разделе **повторите-кроме** инструкции и его результат — переход в конец защищенного раздела. Выполнение продолжается с первого оператора, следующего за обработчиком исключений.

Объект `goto` оператор также может переходить из защищенного раздела, а не снижает производительность, нежели в **try-finally** инструкции поскольку очистки стека не выполняется. Тем не менее вместо оператора `__leave` мы рекомендуем использовать ключевое слово `goto`, поскольку это снижает вероятность ошибки в крупных или сложных защищенных разделах.

### <a name="structured-exception-handling-intrinsic-functions"></a>Встроенные функции структурированной обработки исключений

Структурированная обработка исключений имеет две встроенных функции, которые можно использовать с **повторите-кроме** инструкции: `GetExceptionCode` и `GetExceptionInformation`.

`GetExceptionCode`Возвращает код исключения (32-разрядное целочисленное значение).

Встроенная функция `GetExceptionInformation` возвращает указатель на структуру, содержащую Дополнительные сведения об исключении. Через этот указатель можно обращаться к состоянию компьютера, которое существовало в момент возникновения аппаратного исключения. Эта структура выглядит следующим образом:

```cpp  
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS; 
```  

Типы указателей `PEXCEPTION_RECORD` и `PCONTEXT` определены во включаемом файле WINNT. Символ «H» и `_EXCEPTION_RECORD` и `_CONTEXT` определены во включаемом файле EXCPT. H

Можно использовать `GetExceptionCode` в обработчике исключений. Тем не менее, можно использовать `GetExceptionInformation` только в выражении фильтра исключения. Обычно она указывает на сведения, которые хранятся в стеке и уже недоступны в тот момент, когда управление передаются обработчику исключений.

Встроенная функция `AbnormalTermination` можно использовать в обработчик завершения. Возвращает 0, если тело **try-finally** инструкция завершается последовательным выполнением. В остальных случаях функция возвращает 1.

Во включаемом файле EXCPT.H определены альтернативные имена этих встроенных функций:

`GetExceptionCode`эквивалентно`_exception_code`

 `GetExceptionInformation`эквивалентно`_exception_info`

 `AbnormalTermination`эквивалентно`_abnormal_termination`
  
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
  
## <a name="output"></a>Вывод  
  
```  
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

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
[Структурированных исключений, обработки (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
[Ключевые слова](../cpp/keywords-cpp.md)
