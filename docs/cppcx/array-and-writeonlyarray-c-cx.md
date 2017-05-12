---
title: "Классы Array и WriteOnlyArray (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# Классы Array и WriteOnlyArray (C++/CX)
Можно беспрепятственно использовать обычные массивы в стиле языка C или [std::array](../standard-library/array-class-stl.md) в программе [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] \(хотя зачастую удобнее использовать [std::vector](../Topic/vector%20Class%201.md)\), но в любом API, опубликованном в метаданных, необходимо преобразовать массив или вектор в стиле языка C в соответствующий тип [Platform::Array](../cppcx/platform-array-class.md) или [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) в зависимости от способа его использования. Тип [Platform::Array](../cppcx/platform-array-class.md) не сравним по эффективности и широте возможностей с типом [std::vector](../Topic/vector%20Class%201.md), поэтому в общем случае не рекомендуется использовать его во внутреннем коде, который выполняет множество операций над элементами массива.  
  
 Следующие типы массивов могут передаваться через ABI:  
  
1.  const Platform::Array^  
  
2.  Platform::Array^\*  
  
3.  Platform::WriteOnlyArray  
  
4.  возвращаемое значение Platform::Array^  
  
 Эти типы массивов следует использовать для реализации трех типов шаблонов массивов, определенных в [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 PassArray  
 Используется, когда вызывающий объект передает массив методу. Тип входного параметра C\+\+ — `const`[Platform::Array](../cppcx/platform-array-class.md)\<T\>.  
  
 FillArray  
 Используется, когда вызывающий объект передает массив методу для заполнения. Тип входного параметра C\+\+ — [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T\>.  
  
 ReceiveArray  
 Используется, когда вызывающий объект получает массив, выделяемый методом. В C\+\+\/CX массив можно вернуть в возвращаемом значении в виде Array^ или в качестве выходного параметра типа Array^\*.  
  
## Шаблон PassArray  
 Если клиентский код передает массив в метод C\+\+, который не изменяет его, метод принимает массив как const Array^. На уровне двоичного интерфейса приложений \(ABI\) [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] этот массив называется PassArray. В следующем примере показано, как передать массив, выделенный в JavaScript функции C\+\+, которая считывает из него.  
  
 [!code-javascript[cx_arrays#101](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#101)]  
  
 В следующем фрагменте кода показан метод C\+\+:  
  
 [!code-cpp[cx_arrays#01](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#01)]  
  
## Шаблон ReceiveArray  
 В шаблоне ReceiveArray клиентский код объявляет массив и передает его методу, который выделяет память для массива и инициализирует его. Тип входного параметра C\+\+ — указатель в виде "крышки": `Array<T>^*`. В следующем примере показано, как объявить объект массива в JavaScript и передать его функции C\+\+, которая выделяет память, инициализирует элементы и возвращает массив в JavaScript. JavaScript обрабатывает выделенный массив в качестве возвращаемого значения, но функция C\+\+ обрабатывает его как выходной параметр.  
  
 [!code-javascript[cx_arrays#102](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#102)]  
  
 В следующем фрагменте кода показаны два способа реализации метода C\+\+:  
  
 [!code-cpp[cx_arrays#02](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#02)]  
  
## Заполнение массивов  
 Если необходимо выделить массив в вызывающем объекте, а затем инициализировать или изменить его в вызываемом объекте, используйте массив `WriteOnlyArray`. В следующем примере показано, как реализовать функцию C\+\+, которая использует `WriteOnlyArray` и вызывает его из JavaScript.  
  
 [!code-javascript[cx_arrays#103](../snippets/javascript/VS_Snippets_Misc/cx_arrays/javascript/default.js#103)]  
  
 В следующем фрагменте кода показано, как реализовать метод C\+\+:  
  
 [!code-cpp[cx_arrays#03](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#03)]  
  
## Преобразования массивов  
 В этом примере показано, как использовать массив [Platform::Array](../cppcx/platform-array-class.md) для создания других типов коллекций.  
  
 [!code-cpp[cx_arrays#05](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#05)]  
  
 В следующем примере показано, как создать массив [Platform::Array](../cppcx/platform-array-class.md) из массива в стиле языка C и вернуть его из открытого метода.  
  
 [!code-cpp[cx_arrays#06](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.cpp#06)]  
  
## Массивы массивов  
 Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно использовать `IVector<Platform::Array<T>>` в качестве возвращаемого значения или параметра метода в открытом методе. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
## Используйте ArrayReference, чтобы избежать копирования данных  
 В некоторых сценариях, где данные передаются через ABI в [Platform::Array](../cppcx/platform-array-class.md), и в конечном счете должны обрабатываться в массиве в стиле C для большей эффективности, можно использовать [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md), чтобы избежать дополнительного копирования. При передаче [ArrayReference](../cppcx/platform-arrayreference-class.md) в качестве аргумента в параметр, который принимает значение `Platform::Array`, `ArrayReference` сохранит данные непосредственно в указанном массиве в стиле C. Просто учтите, что `ArrayReference` не блокирует исходные данные, и если данные изменяются или удаляются в другом потоке до завершения вызова, результаты будут неопределенными.  
  
 В следующем фрагменте кода показано, как скопировать результаты операции [DataReader](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.datareader.aspx) в `Platform::Array` \(стандартный подход\), а затем заменить `ArrayReference`, чтобы скопировать данные непосредственно в массив в стиле C.  
  
 [!code-cpp[cx_arrays#07](../snippets/cpp/VS_Snippets_Misc/cx_arrays/cpp/class1.h#07)]  
  
## Избегайте использования типа Array в качестве свойства  
 Как правило, следует избегать предоставления доступа к типу `Platform::Array` как к свойству в ссылочном классе, потому что массив возвращается целиком, даже если код клиента пытается получить доступ только к одному элементу. При необходимости предоставить доступ к контейнеру последовательности как к свойству открытого ссылочного класса лучше использовать класс [Windows::Foundation::IVector](http://msdn.microsoft.com/library/windows/apps/br206631.aspx). В закрытых и внутренних API \(которые не публикуются в метаданных\) рекомендуется использовать стандартный контейнер C\+\+, такой как [std::vector](../Topic/vector%20Class%201.md).  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)