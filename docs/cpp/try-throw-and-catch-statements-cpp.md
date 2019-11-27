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
ms.openlocfilehash: 31ed5f7a17b9b45dbbecf5ccb29d2b51a7635eaa
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245144"
---
# <a name="try-throw-and-catch-statements-c"></a>Операторы try, throw и catch (C++)

Чтобы реализовать обработку исключений в C++, используйте выражения **try**, **throw**и **catch** .

Во-первых, используйте блок **try** , чтобы заключить одну или несколько инструкций, которые могут вызвать исключение.

Выражение **throw** сигнализирует о том, что в блоке **try** возникло исключительное условие — часто — ошибка. В качестве операнда выражения **throw** можно использовать объект любого типа. Обычно этот объект используется для передачи информации об ошибке. В большинстве случаев рекомендуется использовать класс [std:: Exception](../standard-library/exception-class.md) или один из производных классов, определенных в стандартной библиотеке. Если один из них не подходит, рекомендуется создать собственный производный класс исключений из `std::exception`.

Чтобы обрабатывать исключения, которые могут возникать, реализуйте один или несколько блоков **catch** сразу после блока **try** . Каждый блок **catch** указывает тип исключения, которое может быть обработано.

В этом примере показан блок **try** и его обработчики. Предположим, `GetNetworkResource()` получает данные через сетевое подключение, а 2 типа исключений являются определенными пользователем классами, производными от `std::exception`. Обратите внимание, что исключения перехватываются ссылкой на **константу** в операторе **catch** . Рекомендуется создавать исключения по значению и захватывать их ссылкой константы.

## <a name="example"></a>Пример

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>Примечания

Код после предложения **try** является защищенным разделом кода. Выражение **throw** вызывает *,* то есть вызывает исключение. Блок кода после предложения **catch** является обработчиком исключений. Это обработчик, который *перехватывает* исключение, возникающее, если типы в выражениях **throw** и **catch** совместимы. Список правил, регулирующих сопоставление типов в блоках **catch** , см. в разделе [Вычисление блоков catch](../cpp/how-catch-blocks-are-evaluated-cpp.md). Если оператор **catch** задает многоточие (...) вместо типа, блок **catch** обрабатывает все типы исключений. При компиляции с параметром [/EHa](../build/reference/eh-exception-handling-model.md) они могут включать структурированные исключения C и созданные системой или асинхронные исключения, такие как защита памяти, деление на ноль и нарушения операций с плавающей запятой. Так как блоки **catch** обрабатываются в порядке программ для поиска соответствующего типа, обработчик многоточия должен быть последним обработчиком для связанного блока **try** . Используйте `catch(...)` осторожно, не позволяйте программе продолжать выполнение, если блоку catch не известно, как обработать конкретное перехваченное исключение. Как правило, блок `catch(...)` используется для ведения журнала ошибок и выполнения специальной очистки перед остановкой выполнения программы.

Выражение **throw** , не имеющее операнда, повторно создает исключение, которое сейчас обрабатывается. Рекомендуется использовать эту форму при повторном создании исключения, поскольку это позволяет сохранить исходные сведения полиморфного типа исключения. Такое выражение должно использоваться только в обработчике **catch** или в функции, которая вызывается из обработчика **catch** . Вновь созданный объект исключения представляет собой исходный объект исключения, а не его копию.

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>См. также:

[Современные C++ рекомендации по исключениям и обработке ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)