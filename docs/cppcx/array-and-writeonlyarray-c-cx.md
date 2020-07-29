---
title: Классы Array и WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: 1980fbcd1e2fa8cdaa48e00d2e7de9e45ac96a92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231030"
---
# <a name="array-and-writeonlyarray-ccx"></a>Классы Array и WriteOnlyArray (C++/CX)

Можно свободно использовать обычные массивы в стиле C или [`std::array`](../standard-library/array-class-stl.md) в программе C++/CX (хотя [`std::vector`](../standard-library/vector-class.md) часто является лучшим выбором), но в любом API, опубликованном в метаданных, необходимо преобразовать массив или вектор в стиле C в [`Platform::Array`](../cppcx/platform-array-class.md) тип или в [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) зависимости от того, как он используется. [`Platform::Array`](../cppcx/platform-array-class.md)Тип не является ни эффективным, ни мощным [`std::vector`](../standard-library/vector-class.md) , так что в качестве общего правила следует избегать его использования во внутреннем коде, который выполняет множество операций с элементами массива.

Следующие типы массивов могут передаваться через ABI:

1. `const Platform::Array^`

1. `Platform::Array^*`

1. `Platform::WriteOnlyArray`

1. Возвращаемое значение`Platform::Array^`

Эти типы массивов используются для реализации трех типов шаблонов массивов, определяемых среда выполнения Windows.

Пассаррай \
Используется, когда вызывающий объект передает массив методу. Тип входного параметра C++ — **`const`** [`Platform::Array`](../cppcx/platform-array-class.md) \<T> .

FillArray
Используется, когда вызывающий объект передает массив методу для заполнения. Тип входного параметра C++ — [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) \<T> .

Рецеивеаррай \
Используется, когда вызывающий объект получает массив, выделяемый методом. В C++/CX массив можно вернуть в возвращаемом значении в виде Array^ или в качестве выходного параметра типа Array^*.

## <a name="passarray-pattern"></a>Шаблон PassArray

Когда клиентский код передает массив в метод C++, а метод не изменяет его, метод принимает массив как `const Array^` . На уровне двоичного интерфейса приложения среда выполнения Windows (ABI) это называется *пассаррай*. В следующем примере показано, как передать массив, выделенный в JavaScript функции C++, которая считывает из него.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

В следующем фрагменте кода показан метод C++:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>Шаблон ReceiveArray

В шаблоне *рецеивеаррай* клиентский код объявляет массив и передает его методу, который выделяет память для него и инициализирует ее. Тип входного параметра C++ — это указатель на Hat: `Array<T>^*` . В следующем примере показано, как объявить объект массива в JavaScript и передать его функции C++, которая выделяет память, инициализирует элементы и возвращает массив в JavaScript. JavaScript обрабатывает выделенный массив в качестве возвращаемого значения, но функция C++ обрабатывает его как выходной параметр.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

В следующем фрагменте кода показаны два способа реализации метода C++:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Заполнение массивов

Если необходимо выделить массив в вызывающем объекте, а затем инициализировать или изменить его в вызываемом объекте, используйте массив `WriteOnlyArray`. В следующем примере показано, как реализовать функцию C++, которая использует `WriteOnlyArray` и вызывает его из JavaScript.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

В следующем фрагменте кода показано, как реализовать метод C++:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Преобразования массивов

В этом примере показано, как использовать [`Platform::Array`](../cppcx/platform-array-class.md) для создания других типов коллекций:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

В следующем примере показано, как создать объект [`Platform::Array`](../cppcx/platform-array-class.md) из массива в стиле C и вернуть его из открытого метода.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Массивы массивов

Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно использовать `IVector<Platform::Array<T>>` в качестве возвращаемого значения или параметра метода в открытом методе. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Используйте ArrayReference, чтобы избежать копирования данных

В некоторых сценариях, где данные передаются по интерфейсу ABI в [`Platform::Array`](../cppcx/platform-array-class.md) , и в конечном итоге требуется обработать эти данные в массиве в стиле C для повышения эффективности, можно использовать [Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) , чтобы избежать дополнительной операции копирования. При передаче в [`Platform::ArrayReference`](../cppcx/platform-arrayreference-class.md) качестве аргумента в параметр, который принимает `Platform::Array` , `ArrayReference` данные будут храниться непосредственно в указанном массиве в стиле C. Просто учтите, что `ArrayReference` не блокирует исходные данные, и если данные изменяются или удаляются в другом потоке до завершения вызова, результаты будут неопределенными.

В следующем фрагменте кода показано, как скопировать результаты [`DataReader`](/uwp/api/windows.storage.streams.datareader) операции в `Platform::Array` (обычный шаблон), а затем заменить `ArrayReference` на копирование данных непосредственно в массив в стиле C:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Избегайте использования типа Array в качестве свойства

Как правило, следует избегать предоставления доступа к типу `Platform::Array` как к свойству в ссылочном классе, потому что массив возвращается целиком, даже если код клиента пытается получить доступ только к одному элементу. Если необходимо предоставить контейнер последовательности как свойство в открытом классе ссылки, [`Windows::Foundation::IVector`](/uwp/api/windows.foundation.collections.ivector-1) лучше выбрать. В закрытых или внутренних интерфейсах API (которые не публикуются в метаданных) рассмотрите возможность использования стандартного контейнера C++, такого как [`std::vector`](../standard-library/vector-class.md) .

## <a name="see-also"></a>См. также статью

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
