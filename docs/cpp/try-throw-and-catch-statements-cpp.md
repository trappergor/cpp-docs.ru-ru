---
title: "Операторы try, throw и catch (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "catch_cpp"
  - "throw"
  - "try_cpp"
  - "try"
  - "throw_cpp"
  - "catch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "catch - ключевое слово [C++]"
  - "ключевые слова [C++], обработка исключений"
  - "Обработка исключений с ++, синтаксис оператора"
  - "try-catch-ключевое слово [C++] сведения об обработке исключений try-catch"
  - "throw - ключевое слово [C++]"
  - "try-catch - ключевое слово [C++]"
  - "try-catch-ключевое слово [C++], обработка исключений"
  - "Создание исключений, throw-ключевое слово"
  - "try-catch-ключевое слово [C++], throw-ключевое слово [C++] s"
  - "Создание исключений, реализация обработки исключений в C++"
  - "создание исключений"
  - "throw-ключевое слово [C++], throw() или throw(...)"
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Операторы try, throw и catch (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для реализации обработки исключений в C++ используйте выражения `try`, `throw` и `catch`.  
  
 Сначала используйте блок `try` для включения одного или нескольких операторов, которые могут создавать исключение.  
  
 Выражение `throw` означает, что исключительное условие, что часто является ошибкой, произошло в блоке `try`. В качестве операнда выражения `throw` можно использовать объект любого типа. Обычно этот объект используется для передачи информации об ошибке. В большинстве случаев рекомендуется использовать [std::exception](../standard-library/exception-class1.md) класс или один из производных классов, которые определены в стандартной библиотеке. Если один из них не подходит, рекомендуется создать собственный производный класс исключений из `std::exception`.  
  
 Для обработки исключений, которые могут быть созданы, необходимо реализовать один или несколько блоков `catch` сразу после блока `try`. Каждый блок `catch` указывает тип исключения, которое он может обрабатывать.  
  
 В этом примере показан блок `try` и его обработчики. Предположим, `GetNetworkResource()` получает данные через сетевое подключение, а 2 типа исключений являются определенными пользователем классами, производными от `std::exception`. Обратите внимание, что исключения перехватываются ссылкой `const` в операторе `catch`. Рекомендуется создавать исключения по значению и захватывать их ссылкой константы.  
  
## <a name="example"></a>Пример  
  
```  
  
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
 Сразу за предложением `try` находится защищенный раздел кода.  `throw` Выражение *вызывает*— создает — исключение. Блок кода после предложения `catch` является обработчиком исключения. Это обработчик, *перехватывает* исключения, если типы в `throw` и `catch` выражения совместимы. Список правил, управляющих сопоставление типов в `catch` блоки, в разделе [вычисляются как блоки Catch](../Topic/How%20Catch%20Blocks%20are%20Evaluated%20\(C++\).md). Если оператор `catch` задает многоточие (...) вместо типа, блок `catch` обрабатывает все типы исключений. При компиляции с [/EHa](../build/reference/eh-exception-handling-model.md) параметр, их число могут входить структурированные исключения C и создаваемые системой или приложением асинхронные исключения, например памяти нарушения защиты, деления на ноль и с плавающей запятой. Поскольку блоки `catch` обрабатываются в порядке программы для поиска подходящего типа, обработчик с многоточием должен быть последним обработчиком для соответствующего блока `try`. Используйте `catch(...)` осторожно, не позволяйте программе продолжать выполнение, если блоку catch не известно, как обработать конкретное перехваченное исключение. Как правило, блок `catch(...)` используется для ведения журнала ошибок и выполнения специальной очистки перед остановкой выполнения программы.  
  
 Выражение `throw` без операндов повторно создает обрабатываемое в данный момент исключение. Рекомендуется использовать эту форму при повторном создании исключения, поскольку это позволяет сохранить исходные сведения полиморфного типа исключения. Такое выражение следует использовать только в обработчике `catch` или в функции, вызываемой из обработчика `catch`. Вновь созданный объект исключения представляет собой исходный объект исключения, а не его копию.  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions – dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>См. также раздел  
 [Обработка исключений с ++](../cpp/cpp-exception-handling.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)