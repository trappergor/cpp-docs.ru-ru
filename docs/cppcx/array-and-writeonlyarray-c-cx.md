---
title: Классы Array и WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: e050fad38d4f70c651fc0ebfddb51a33e31da6f3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032412"
---
# <a name="array-and-writeonlyarray-ccx"></a>Классы Array и WriteOnlyArray (C++/CX)

Вы можете свободно использовать обычные массивы C-стиля или [std::array](../standard-library/array-class-stl.md) в программе C'/CX (хотя [std::vector](../standard-library/vector-class.md) часто является лучшим выбором), но в любом API, который публикуется в метаданных, необходимо преобразовать c-стиль массива или вектор в [платформу::Array](../cppcx/platform-array-class.md) или [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) тип в зависимости от того, как он используется. Тип [Platform::Array](../cppcx/platform-array-class.md) не сравним по эффективности и широте возможностей с типом [std::vector](../standard-library/vector-class.md), поэтому в общем случае не рекомендуется использовать его во внутреннем коде, который выполняет множество операций над элементами массива.

Следующие типы массивов могут передаваться через ABI:

1. const Platform::Array^

1. Platform::Array^*

1. Platform::WriteOnlyArray

1. возвращаемое значение Platform::Array^

Эти типы массивов используются для реализации трех типов шаблонов массивов, определяемых Runtime Windows.

PassArray используется при переходе вызываемого массива к методу. Тип ввода C's `const` [platform::Array](../cppcx/platform-array-class.md)\<T>.

FillArray Используется, когда абонент проходит массив для заполнения метода. Тип ввода C's [platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T>.

ReceiveArray используется при получении массива, который выделяет метод. В C++/CX массив можно вернуть в возвращаемом значении в виде Array^ или в качестве выходного параметра типа Array^*.

## <a name="passarray-pattern"></a>Шаблон PassArray

Если клиентский код передает массив в метод C++, который не изменяет его, метод принимает массив как const Array^. На уровне двоичного интерфейса приложения Windows Runtime (ABI) это называется PassArray. В следующем примере показано, как передать массив, выделенный в JavaScript функции C++, которая считывает из него.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

В следующем фрагменте кода показан метод C++:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>Шаблон ReceiveArray

В шаблоне ReceiveArray клиентский код объявляет массив и передает его методу, который выделяет память для массива и инициализирует его. Тип ввода ввода C's является указателем `Array<T>^*`на шляпу: . В следующем примере показано, как объявить объект массива в JavaScript и передать его функции C++, которая выделяет память, инициализирует элементы и возвращает массив в JavaScript. JavaScript обрабатывает выделенный массив в качестве возвращаемого значения, но функция C++ обрабатывает его как выходной параметр.

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

В следующем фрагменте кода показано, как скопировать результаты операции [DataReader](/uwp/api/windows.storage.streams.datareader) в `Platform::Array` (стандартный подход), а затем заменить `ArrayReference` , чтобы скопировать данные непосредственно в массив в стиле C.

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Избегайте использования типа Array в качестве свойства

Как правило, следует избегать предоставления доступа к типу `Platform::Array` как к свойству в ссылочном классе, потому что массив возвращается целиком, даже если код клиента пытается получить доступ только к одному элементу. При необходимости предоставить доступ к контейнеру последовательности как к свойству открытого ссылочного класса лучше использовать класс [Windows::Foundation::IVector](/uwp/api/windows.foundation.collections.ivector-1) . В закрытых и внутренних API (которые не публикуются в метаданных) рекомендуется использовать стандартный контейнер C++, такой как [std::vector](../standard-library/vector-class.md).

## <a name="see-also"></a>См. также раздел

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Ссылка на язык СЗ/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ссылка на имены](../cppcx/namespaces-reference-c-cx.md)
