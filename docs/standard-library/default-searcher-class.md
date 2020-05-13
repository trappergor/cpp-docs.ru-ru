---
title: класс default_searcher
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 2c8b93b83b271f787c993f789e1a68f84a60f016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368924"
---
# <a name="default_searcher-class"></a>класс default_searcher

A `default_searcher` — это тип объекта функции для операций, которые ищут последовательность, указанную в конструкторе объекта. Поиск выполняется в рамках другой последовательности, предоставляемой оператору вызова функции объекта. Вызывает `default_searcher` [std::поиск](algorithm-functions.md#search) для выполнения поиска.

## <a name="syntax"></a>Синтаксис

```cpp
template <class ForwardIterator, class BinaryPredicate = equal_to<>>
class default_searcher
{
    default_searcher(
        ForwardIterator pat_first,
        ForwardIterator pat_last,
        BinaryPredicate pred = BinaryPredicate());

    template <class ForwardIterator2>
    pair<ForwardIterator2, ForwardIterator2> operator()(
        ForwardIterator2 first,
        ForwardIterator2 last) const;
};
```

## <a name="members"></a>Участники

| | |
| - | - |
| **Конструктор** | |
| [default_searcher](#default-searcher-constructor) | |
| **Операторы** | |
| [оператор()](#operator-call) | |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a>default_searcher конструктор

Строит объект `default_searcher` функции, используя последовательность для поиска и предиката равенства.

```cpp
default_searcher(                   // C++17
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());

constexpr default_searcher(         // C++20
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Параметры

*pat_first*\
Первоначальный элемент последовательности для поиска.

*pat_last*\
Конец последовательности для поиска.

*Pred*\
Факультативное сравнение равенства предикат для элементов последовательности. Если тип сравнения равенства не указан, `std::equal_to`по умолчанию .

### <a name="remarks"></a>Remarks

Бросает любое исключение, брошенное конструктором копий типов *BinaryPredicate* или *ForwardIterator.*

Этот класс является новым в C-17. Конструкция сделана `constexpr`СЗ-20.

## <a name="operator"></a><a name="operator-call"></a>оператор()

Оператор вызова оператора функции. Поиск в последовательности `[first, last)` аргументов для последовательности, указанной конструктору.

```cpp
template <class ForwardIterator2>   // C++17
pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;

template <class ForwardIterator2>   // C++20
constexpr pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;
```

### <a name="parameters"></a>Параметры

*Первый*\
Первоначальный элемент последовательности для поиска внутри.

*Последний*\
Конец последовательности для поиска внутри.

### <a name="remarks"></a>Remarks

Возвращает пару итераторов. Первоначальный итератор *i* является эффективным результатом:

`std::search( first, last, pat_first, pat_last, pred )`.

Второй итератор пары является *последним,* если *я*й является *последним*. В противном случае, это эффективный результат:

`std::next( i, std::distance( pat_first, pat_last ))`.

Этот класс является новым в C-17. С-20 сделал оператор `constexpr`омование .

## <a name="see-also"></a>См. также раздел

[\<функциональный>](functional.md)\
[функции алгоритма](algorithm-functions.md)\
[std::поиск](algorithm-functions.md#search)
