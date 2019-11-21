---
title: Проверка блоков Catch (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
ms.openlocfilehash: 027dc87923a588ea891dbf6dd835e2baba75a1cb
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245856"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Проверка блоков Catch (C++)

C++ позволяет создавать исключения любого типа, хотя обычно рекомендуется создавать типы, производные от std::exception. A C++ exception can be caught by a **catch** handler that specifies the same type as the thrown exception, or by a handler that can catch any type of exception.

Если созданное исключение имеет тип класса, у которого имеется один или несколько базовых классов, то его могут перехватывать обработчики, которые принимают базовые классы (и ссылки на базовые классы) этого типа исключения. Обратите внимание, что если исключение перехватывается по ссылке, то оно привязывается к самому объекту исключения; в противном случае обрабатывается его копия (как и в случае с аргументами функции).

When an exception is thrown, it may be caught by the following types of **catch** handlers:

- Обработчик, который может принимать любой тип данных (синтаксис с многоточием).

- A handler that accepts the same type as the exception object; because it is a copy, **const** and **volatile** modifiers are ignored.

- Обработчик, который принимает ссылку на тот же тип, что и у объекта исключения.

- A handler that accepts a reference to a **const** or **volatile** form of the same type as the exception object.

- A handler that accepts a base class of the same type as the exception object; since it is a copy, **const** and **volatile** modifiers are ignored. The **catch** handler for a base class must not precede the **catch** handler for the derived class.

- Обработчик, который принимает ссылку на базовый класс того же типа, что и у объекта исключения.

- A handler that accepts a reference to a **const** or **volatile** form of a base class of the same type as the exception object.

- Обработчик, который принимает указатель, в который можно преобразовать созданный объект указателя при помощи стандартных правил преобразования указателей.

The order in which **catch** handlers appear is significant, because handlers for a given **try** block are examined in order of their appearance. Например, ошибкой будет поместить обработчик для базового класса перед обработчиком для производного класса. After a matching **catch** handler is found, subsequent handlers are not examined. As a result, an ellipsis **catch** handler must be the last handler for its **try** block. Пример:

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

In this example, the ellipsis **catch** handler is the only handler that is examined.

## <a name="see-also"></a>См. также

[Modern C++ best practices for exceptions and error handling](../cpp/errors-and-exception-handling-modern-cpp.md)