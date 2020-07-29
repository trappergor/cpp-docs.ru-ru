---
title: '&lt;vector&gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 4e9f3e4a35cd772897e326fafedf359062e6128b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224530"
---
# <a name="ltvectorgt"></a>&lt;vector&gt;

Определяет вектор шаблона класса контейнера и несколько вспомогательных шаблонов.

`vector` — это контейнер, который упорядочивает элементы данного типа в виде линейной последовательности. Он обеспечивает быстрый произвольный доступ к любому элементу и позволяет динамически добавлять элементы в последовательность и удалять их. `vector` является наиболее подходящим типом контейнера для последовательности, когда на первом месте стоит производительность произвольного доступа.

> [!NOTE]
> \<vector>Библиотека также использует `#include <initializer_list>` инструкцию.

Подробнее о классе `vector` см. в разделе [Класс vector](../standard-library/vector-class.md). Дополнительные сведения о специализации `vector<bool>` см. в разделе [ \<bool> класс Vector](../standard-library/vector-bool-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
namespace std {
template <class Type, class Allocator>
class vector;
template <class Allocator>
class vector<bool>;

template <class Allocator>
struct hash<vector<bool, Allocator>>;

// TEMPLATE FUNCTIONS
template <class Type, class Allocator>
bool operator== (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator!= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<(
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator> (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator>= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
void swap (
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Параметры

*Тип*\
Параметр-шаблон для типа данных, хранящихся в векторе.

*Выделен*\
Параметр-шаблон для хранимого объекта распределителя, отвечающего за выделение и освобождение памяти.

*слева*\
Первый (левый) вектор в операции сравнения.

*Правильно*\
Второй (правый) вектор в операции сравнения.

## <a name="members"></a>Элементы

### <a name="operators"></a>Операторы

|||
|-|-|
|[станции! =](../standard-library/vector-operators.md#op_neq)|Проверяет следующее условие: объект вектора слева от оператора не равен объекту вектора справа от оператора.|
|[Оператор<](../standard-library/vector-operators.md#op_lt)|Проверяет следующее условие: объект вектора слева от оператора меньше, чем объект вектора справа от оператора.|
|[оператор\<=](../standard-library/vector-operators.md#op_gt_eq)|Проверяет следующее условие: объект вектора слева от оператора меньше или равен объекту вектора справа от оператора.|
|[Оператор = =](../standard-library/vector-operators.md#op_eq_eq)|Проверяет следующее условие: объект вектора слева от оператора равен объекту вектора справа от оператора.|
|[Оператор>](../standard-library/vector-operators.md#op_gt)|Проверяет следующее условие: объект вектора слева от оператора больше, чем объект вектора справа от оператора.|
|[Оператор>=](../standard-library/vector-operators.md#op_gt_eq)|Проверяет следующее условие: объект вектора слева от оператора больше или равен объекту вектора справа от оператора.|

### <a name="classes"></a>Классы

|||
|-|-|
|[Класс Vector](../standard-library/vector-class.md)|Шаблон класса контейнеров последовательностей для хранения элементов заданного типа в линейном порядке и быстрого произвольного доступа к любому элементу.|

### <a name="specializations"></a>Специализации

|||
|-|-|
|hash|Возвращает хэш вектора.|
|[\<bool>класс Vector](../standard-library/vector-bool-class.md)|Полная специализация вектора шаблона класса для элементов типа **`bool`** с распределителем для базового типа, используемого специализацией.|

## <a name="requirements"></a>Требования

**Заголовок:**\<vector>

**Пространство имен:** std

## <a name="see-also"></a>См. также статью

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
