---
title: класс boyer_moore_horspool_searcher
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: 4d404b414ad632e02be5f4e9fad0e22cefb86ce2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366781"
---
# <a name="boyer_moore_horspool_searcher-class"></a>класс boyer_moore_horspool_searcher

Класс `boyer_moore_horspool_searcher` представляет собой тип объекта функции, который использует алгоритм Бойера-Мура-Хорспула для поиска последовательности, указанной в конструкторе объекта. Поиск выполняется в рамках другой последовательности, предоставляемой оператору вызова функции объекта. Этот класс передается в качестве параметра одной из перегрузок [std::Search](algorithm-functions.md#search).

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
| **Операторы** | |
| [оператор()](#operator-call) | |

## <a name="boyer_moore_horspool_searcher-constructor"></a><a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher конструктор

Строит объект `boyer_moore_horspool_searcher` функции, используя последовательность для поиска объекта хэш-функции и предикат равенства.

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Параметры

*pat_first*\
Первоначальный элемент последовательности для поиска.

*pat_last*\
Конец последовательности для поиска.

*Hf*\
Callable объект, используемый для хэширования элементов последовательности.

*Pred*\
Факультативное сравнение равенства предикат для элементов последовательности. Если тип сравнения равенства не указан, `std::equal_to`по умолчанию .

### <a name="remarks"></a>Remarks

Бросает любое исключение, брошенное конструктором копии *BinaryPredicate,* *Hash*, или *RandomAccessIterator* типов, или оператор вызова *BinaryPredicate* или *Хэш*.

Этот класс является новым в C-17.

## <a name="operator"></a><a name="operator-call"></a>оператор()

Оператор вызова объекта функции. Поиск в последовательности `[first, last)` аргументов для последовательности, указанной конструктору.

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Параметры

*Первый*\
Первоначальный элемент последовательности для поиска внутри.

*Последний*\
Конец последовательности для поиска внутри.

### <a name="remarks"></a>Remarks

Если шаблон `[pat_first, pat_last)` поиска пуст, `make_pair(first, first)`возвращается . Если шаблон поиска не найден, `make_pair(last, last)`возвращается. В противном случае, возвращает пару итераторов в `[first, last)` начало и `[pat_first, pat_last)` конец последовательности в том, что равно в соответствии с *предикатом pred*.

Этот класс является новым в C-17.

## <a name="see-also"></a>См. также раздел

[\<функциональный>](functional.md)\
[функции алгоритма](algorithm-functions.md)\
[класс boyer_moore_searcher](boyer-moore-searcher-class.md)\
[std::поиск](algorithm-functions.md#search)
