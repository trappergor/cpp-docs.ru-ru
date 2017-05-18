---
title: "Класс integer_sequence   Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
- integer_sequence
dev_langs:
- C++
helpviewer_keywords:
- integer_sequence
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 533bb3094949d0f339f67fade4e199a6210b2d26
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="integersequence-class"></a>Класс integer_sequence
Представляет последовательность целых чисел. Может использоваться для извлечения и развертывания пакетов параметров в типах с переменным числом аргументов, например std::tuple\<T.... >, которые передаются в функцию в качестве аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <class T, T... Vals>  
struct integer_sequence  
```  
  
#### <a name="parameters"></a>Параметры  
 T  
 Тип значений. Это должен быть целочисленный тип: bool, char, char16_t, char32_t, wchar_t или целочисленный тип со знаком или без знака.  
  
 Vals  
 Пакет параметров, не являющихся типами, представляющий последовательность значений целочисленного типа T.  
  
## <a name="members"></a>Члены  
  
|||  
|-|-|  
|`static size_t size() noexcept`|Число элементов в последовательности.|  
|Определение типа T value_type|Тип каждого элемента последовательности. Должен быть целочисленным типом.|  
  
## <a name="remarks"></a>Примечания  
 Пакет параметров, который передается непосредственно в функцию, может быть распакован без использования специальных вспомогательных методов библиотеки. Когда пакет параметров входит в тип, передаваемый в функцию, и вам необходимы индексы для доступа к элементам, то самым простым способом распаковать его будет использование `integer_sequence` и связанных с ним псевдонимов типа `make_integer_sequence`, `index_sequence`, `make_index_sequence` и `index_sequence_for`.  
  
## <a name="example"></a>Пример  
 Следующий пример основан на исходном предложении [N3658](http://open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html). В нем продемонстрирован способ использования `integer_sequence` для создания `std::tuple` из `std::array<T,N>`, и способ использования `integer_sequence` для получения элементов кортежа.  
  
 В функции `a2t` `index_sequence` является псевдонимом `integer_sequence` на основе целочисленного типа `size_t`. `make_index_sequence` — это псевдоним, который во время компиляции создает `index_sequence`, отсчитываемый от нуля, с тем же количеством элементов, как у массива, переданного вызывающим объектом. `a2t` передает `index_sequence` по значению в `a2t_`, где выражение `a[I]...` распаковывает `I`, а затем элементы передаются в `make_tuple`, который использует их как отдельные аргументы. Например, если последовательность содержит три элемента, то `make_tuple` вызывается как make_tuple(a[0], a[1], a[2]). Сами элементы массива, конечно, могут быть любого типа.  
  
 Функция apply принимает аргумент [std::tuple](../standard-library/tuple-class.md) и создает integer_sequence с использованием вспомогательного класса `tuple_size`. Обратите внимание, что [std::decay_t](../standard-library/decay-class.md)_необходим, так как [tuple_size](../standard-library/tuple-size-class-tuple.md) не работает со ссылочными типами. Функция `apply_` распаковывает элементы кортежа и пересылает их как отдельные аргументы при вызове функции. В этом примере функция представляет из себя простое лямбда-выражение, которое выводит значения.  
  
```  
  
#include <stddef.h>  
#include <iostream>  
#include <tuple>  
#include <utility>  
#include <array>  
#include <string>  
  
using namespace std;  
  
// Create a tuple from the array and the index_sequence  
template<typename Array, size_t... I>  
auto a2t_(const Array& a, index_sequence<I...>)  
{  
    return make_tuple(a[I]...);  
}  
  
// Create an index sequence for the array, and pass it to the  
// implementation function a2t_  
template<typename T, size_t N>  
auto a2t(const array<T, N>& a)  
{  
    return a2t_(a, make_index_sequence<N>());  
}  
  
// Call function F with the tuple members as separate arguments.   
template<typename F, typename Tuple = tuple<T...>, size_t... I>  
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)   
{  
    return forward<F>(f)(get<I>(forward<Tuple>(args))...);  
}  
  
// Create an index_sequence for the tuple, and pass it with the   
// function object and the tuple to the implementation function apply_  
template<typename F, typename Tuple = tuple<T...>>  
decltype(auto) apply(F&& f, Tuple&& args)  
{  
    using Indices = make_index_sequence<tuple_size<decay_t<Tuple>>::value >;  
    return apply_(forward<F>(f), forward<Tuple>(args), Indices());  
}  
  
int main()  
{   
    const array<string, 3> arr { "Hello", "from", "C++14" };  
  
    //Create a tuple given a array  
    auto tup = a2t(arr);   
  
    // Extract the tuple elements  
    apply([](const string& a, const string& b, const string& c) {cout << a << " " << b << " " << c << endl; }, tup);  
  
    char c;  
    cin >> c;  
}  
  
```  
  
  Чтобы подготовить `index_sequence` для пакета параметров, используйте `index_sequence_for`\<T...>, который является псевдонимом для `make_index_sequence`\<sizeof...(T)>.  
  
## <a name="requirements"></a>Требования  
 Заголовок: <type_traits>  
  
 Пространство имен: std  
  
## <a name="see-also"></a>См. также  
 [Многоточия и шаблоны с переменным числом аргументов](../cpp/ellipses-and-variadic-templates.md)


