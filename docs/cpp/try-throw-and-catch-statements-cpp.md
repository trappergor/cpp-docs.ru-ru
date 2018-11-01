---
title: Операторы try, throw и catch (C++)
ms.date: 11/04/2016
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
ms.openlocfilehash: 81d954b2e757c692bd80604a3f85ffb8c79c4f85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455735"
---
# <a name="try-throw-and-catch-statements-c"></a>Операторы try, throw и catch (C++)

Чтобы реализовать обработку исключений в C++, используйте **попробуйте**, **throw**, и **catch** выражения.

Во-первых, используйте **попробуйте** блок, чтобы вложить один или несколько операторов, которые могут создавать исключение.

Объект **throw** выражение означает, что исключительным условием — часто является ошибкой, произошло в **попробуйте** блока. Объект любого типа можно использовать как операнд **throw** выражение. Обычно этот объект используется для передачи информации об ошибке. В большинстве случаев мы рекомендуем использовать [std::exception](../standard-library/exception-class.md) класс или один из производных классов, которые определены в стандартной библиотеке. Если один из них не подходит, рекомендуется создать собственный производный класс исключений из `std::exception`.

Для обработки исключений, которые могут произойти, реализует один или несколько **catch** блоки сразу после **попробуйте** блока. Каждый **catch** блока указывает тип исключения, он может обрабатывать.

В этом примере показано **попробуйте** блока и его обработчики. Предположим, `GetNetworkResource()` получает данные через сетевое подключение, а 2 типа исключений являются определенными пользователем классами, производными от `std::exception`. Обратите внимание, что исключения перехватываются **const** в ссылку на **catch** инструкции. Рекомендуется создавать исключения по значению и захватывать их ссылкой константы.

## <a name="example"></a>Пример

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>Примечания

Код после **попробуйте** предложение находится защищенный раздел кода. **Throw** выражение *вызывает*— то есть вызывает — исключение. Блок кода после **catch** предложение является обработчиком исключения. Это обработчик, *перехватывает* исключение, которое возникает, если типы в **throw** и **catch** выражениях совместимы. Список правил, управляющих сопоставление типов в **catch** блоки, см. в разделе [оцениваются как блоки Catch](../cpp/how-catch-blocks-are-evaluated-cpp.md). Если **catch** инструкция задает многоточие (...) вместо типа **catch** блок обрабатывает все типы исключений. При выполнении компиляции с [/EHa](../build/reference/eh-exception-handling-model.md) параметр, они могут включать структурированные исключения C и создаваемые системой или приложением асинхронные исключения, например памяти нарушения защиты, деление на ноль и с плавающей запятой . Так как **catch** блоки обрабатываются в порядке программы для поиска подходящего типа, обработчик с многоточием должен быть последним обработчиком для соответствующего **попробуйте** блока. Используйте `catch(...)` осторожно, не позволяйте программе продолжать выполнение, если блоку catch не известно, как обработать конкретное перехваченное исключение. Как правило, блок `catch(...)` используется для ведения журнала ошибок и выполнения специальной очистки перед остановкой выполнения программы.

Объект **throw** выражение без операндов повторно создает обрабатываемое в данный момент исключение. Рекомендуется использовать эту форму при повторном создании исключения, поскольку это позволяет сохранить исходные сведения полиморфного типа исключения. Такое выражение следует использовать только в **catch** обработчик или функцию, которая вызывается из **catch** обработчика. Вновь созданный объект исключения представляет собой исходный объект исключения, а не его копию.

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>См. также

[Обработка исключений С++](../cpp/cpp-exception-handling.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)