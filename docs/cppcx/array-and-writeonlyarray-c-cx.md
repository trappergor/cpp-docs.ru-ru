---
title: Классы Array и WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: fd616487bd3c11544f12e84a7dc64f41e63d501a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739412"
---
# <a name="array-and-writeonlyarray-ccx"></a>Классы Array и WriteOnlyArray (C++/CX)

Можно свободно использовать обычные массивы в стиле C или [std::array](../standard-library/array-class-stl.md) в C + +/ CX программы (несмотря на то что [std::vector](../standard-library/vector-class.md) часто является наиболее предпочтительной), но в любом API, который публикуется в метаданных, необходимо преобразовать массив в стиле C или вектора синхронизации в [Platform::Array](../cppcx/platform-array-class.md) или [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) типа в зависимости от того, как он используется. Тип [Platform::Array](../cppcx/platform-array-class.md) не сравним по эффективности и широте возможностей с типом [std::vector](../standard-library/vector-class.md), поэтому в общем случае не рекомендуется использовать его во внутреннем коде, который выполняет множество операций над элементами массива.

Следующие типы массивов могут передаваться через ABI:

1. const Platform::Array^

1. Platform::Array^*

1. Platform::WriteOnlyArray

1. возвращаемое значение Platform::Array^

Использовать эти типы массивов для реализации трех типов шаблонов массивов, определяемые средой выполнения Windows.

PassArray используется, когда вызывающий объект передает массив в метод. Тип входного параметра C++ — `const` [Platform::Array](../cppcx/platform-array-class.md)\<T >.

FillArray используется, когда вызывающий объект передает массив в метод для заполнения. Тип входного параметра C++ — [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T >.

ReceiveArray используется, когда вызывающий объект получает массив, выделяемый методом. В C++/CX массив можно вернуть в возвращаемом значении в виде Array^ или в качестве выходного параметра типа Array^*.

## <a name="passarray-pattern"></a>Шаблон PassArray

Если клиентский код передает массив в метод C++, который не изменяет его, метод принимает массив как const Array^. На уровне двоичного интерфейса (ABI) приложения среды выполнения Windows это называется PassArray. В следующем примере показано, как передать массив, выделенный в JavaScript функции C++, которая считывает из него.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

В следующем фрагменте кода показан метод C++:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>Шаблон ReceiveArray

В шаблоне ReceiveArray клиентский код объявляет массив и передает его методу, который выделяет память для массива и инициализирует его. Тип входного параметра C++ — указатель на крышки: `Array<T>^*`. В следующем примере показано, как объявить объект массива в JavaScript и передать его функции C++, которая выделяет память, инициализирует элементы и возвращает массив в JavaScript. JavaScript обрабатывает выделенный массив в качестве возвращаемого значения, но функция C++ обрабатывает его как выходной параметр.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

В следующем фрагменте кода показаны два способа реализации метода C++:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Заполнение массивов

Если необходимо выделить массив в вызывающем объекте, а затем инициализировать или изменить его в вызываемом объекте, используйте массив `WriteOnlyArray`. В следующем примере показано, как реализовать функцию C++, которая использует `WriteOnlyArray` и вызывает его из JavaScript.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

В следующем фрагменте кода показано, как реализовать метод C++:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Преобразования массивов

В этом примере показано, как использовать массив [Platform::Array](../cppcx/platform-array-class.md) для создания других типов коллекций.

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

В следующем примере показано, как создать массив [Platform::Array](../cppcx/platform-array-class.md) из массива в стиле языка C и вернуть его из открытого метода.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Массивы массивов

Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно использовать `IVector<Platform::Array<T>>` в качестве возвращаемого значения или параметра метода в открытом методе. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Используйте ArrayReference, чтобы избежать копирования данных

В некоторых сценариях, где данные передаются через ABI в [Platform::Array](../cppcx/platform-array-class.md), и в конечном счете должны обрабатываться в массиве в стиле C для большей эффективности, можно использовать [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) , чтобы избежать дополнительного копирования. При передаче [ArrayReference](../cppcx/platform-arrayreference-class.md) в качестве аргумента в параметр, который принимает значение `Platform::Array`, `ArrayReference` сохранит данные непосредственно в указанном массиве в стиле C. Просто учтите, что `ArrayReference` не блокирует исходные данные, и если данные изменяются или удаляются в другом потоке до завершения вызова, результаты будут неопределенными.

В следующем фрагменте кода показано, как скопировать результаты операции [DataReader](/uwp/api/Windows.Storage.Streams.DataReader) в `Platform::Array` (стандартный подход), а затем заменить `ArrayReference` , чтобы скопировать данные непосредственно в массив в стиле C.

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Избегайте использования типа Array в качестве свойства

Как правило, следует избегать предоставления доступа к типу `Platform::Array` как к свойству в ссылочном классе, потому что массив возвращается целиком, даже если код клиента пытается получить доступ только к одному элементу. При необходимости предоставить доступ к контейнеру последовательности как к свойству открытого ссылочного класса лучше использовать класс [Windows::Foundation::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) . В закрытых и внутренних API (которые не публикуются в метаданных) рекомендуется использовать стандартный контейнер C++, такой как [std::vector](../standard-library/vector-class.md).

## <a name="see-also"></a>См. также

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
