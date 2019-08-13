---
title: класс boyer_moore_horspool_searcher
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: c7d24fee4a47fc588b00e527594682f1c4aadf76
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957165"
---
# <a name="boyer_moore_horspool_searcher-class"></a>класс boyer_moore_horspool_searcher

`boyer_moore_horspool_searcher` Класс является типом объекта функции, который использует алгоритм Бойера-Мура-хорспул для поиска последовательности, указанной в конструкторе объекта. Поиск выполняется в другой последовательности, предоставленной оператору вызова функции объекта. Этот класс передается в качестве параметра в одну из перегрузок [std:: Search](algorithm-functions.md#search).

## <a name="syntax"></a>Синтаксис

```cpp
template <
    class RandomAccessIterator,
    class Hash = hash<typename iterator_traits<RandomAccessIterator>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_horspool_searcher
{
    boyer_moore_horspool_searcher(
        RandomAccessIterator pat_first,
        RandomAccessIterator pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>Участники

| | |
| - | - |
| **Конструктор** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **Инструкции** | |
| [operator()](#operator-call) | |

## <a name="boyer-moore-horspool-searcher-constructor"></a>Конструктор boyer_moore_horspool_searcher

Конструирует объект функции, используя последовательность для поиска, объект хэш-функции и предикат равенства. `boyer_moore_horspool_searcher`

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Параметры

*pat_first*\
Начальный элемент последовательности для поиска.

*pat_last*\
Конец последовательности для поиска.

*HF*\
Вызываемый объект, используемый для хэширования элементов последовательности.

*Возможен*\
Необязательный предикат сравнения равенства для элементов последовательности. Если тип сравнения на равенство не указан, по умолчанию используется `std::equal_to`значение.

### <a name="remarks"></a>Примечания

Создает исключение, созданное конструктором копий типов *бинарипредикате*, *hash*или *Рандомакцесситератор* , или оператор Call *бинарипредикате* или *hash*.

Этот класс впервые появились в C++ 17.

## <a name="operator-call"></a>оператор ()

Оператор Call объекта Function. Ищет в последовательности `[first, last)` аргументов последовательность, указанную в конструкторе.

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Параметры

*началь*\
Начальный элемент последовательности, в которой необходимо выполнить поиск.

*Последняя*\
Конец последовательности, в которой необходимо выполнить поиск.

### <a name="remarks"></a>Примечания

Если шаблон `[pat_first, pat_last)` поиска пуст, возвращает значение `make_pair(first, first)`. Если шаблон поиска не найден, возвращает `make_pair(last, last)`. В противном случае возвращает пару итераторов в начало и конец последовательности в `[first, last)` таком `[pat_first, pat_last)` же порядке, что и в соответствии с допустимым предикатом.

Этот класс впервые появились в C++ 17.

## <a name="see-also"></a>См. также

[\<functional>](functional.md)\
[функции алгоритма](algorithm-functions.md)\
[класс boyer_moore_searcher](boyer-moore-searcher-class.md)\
[std:: Search](algorithm-functions.md#search)
