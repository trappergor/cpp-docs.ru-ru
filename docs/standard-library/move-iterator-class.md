---
title: Класс move_iterator
ms.date: 03/27/2019
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
helpviewer_keywords:
- std::move_iterator [C++]
- std::move_iterator [C++], iterator_type
- std::move_iterator [C++], iterator_category
- std::move_iterator [C++], value_type
- std::move_iterator [C++], difference_type
- std::move_iterator [C++], pointer
- std::move_iterator [C++], reference
- std::move_iterator [C++], base
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
ms.openlocfilehash: 17af246a85c4e3f1e0c7eb9d387161ad7b5123a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377410"
---
# <a name="move_iterator-class"></a>Класс move_iterator

Шаблон класса `move_iterator` является программой-оболочкой для итератора. Move_iterator предоставляет то же поведение, что и инкапсулируемый в него (хранящийся в нем) итератор, за исключением того, что оператор разыменования хранящегося итератора превращается в ссылку rvalue, что превращает копирование в перемещение. Дополнительные сведения о rvalues см. в разделе [Оператор объявления ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Синтаксис

```cpp
class move_iterator;
```

## <a name="remarks"></a>Remarks

Шаблон класса описывает объект, который ведет себя как итератор, за исключением случаев, когда он был разллирован. Он хранит итератор произвольного доступа типа `Iterator`, доступный посредством функции-члена `base()`. Все операции с итератором `move_iterator` выполняются непосредственно в сохраненном итераторе, за исключением того, что результат `operator*` явным образом приводится к `value_type&&` для создания ссылки rvalue.

Итератор `move_iterator` может выполнять операции, не определенные инкапсулированным итератором. Эти операции не следует использовать.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[move_iterator](#move_iterator)|Конструктор для объектов типа `move_iterator`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[iterator_type](#iterator_type)|Синоним параметра шаблона `RandomIterator`.|
|[iterator_category](#iterator_category)|Синоним более длинного выражения **одноименного имени,** `iterator_category` идентифицирует общие способности итератора.|
|[Value_type](#value_type)|Синоним более длинного выражения **одноименного имени,** `value_type` описывающий тип элементов итератора.|
|[difference_type](#difference_type)|Синоним более длинного выражения **одноименного имени,** `difference_type` описывающий интегральный тип, необходимый для выражения различий между элементами.|
|[указатель](#pointer)|Синоним параметра шаблона `RandomIterator`.|
|[Ссылки](#reference)|Синоним ссылки `rvalue``value_type&&`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[base](#base)|Функция-член возвращает сохраненный итератор, инкапсулированный данным итератором `move_iterator`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[move_iterator:оператор](#op_star)|Возвращает `(reference)*base().`.|
|[move_iterator::оператор](#op_add_add)|Увеличивает значение сохраненного итератора. Точное поведение определяется тем, является ли операция преинкрементной или постинкрементной.|
|[move_iterator:оператор--](#operator--)|Уменьшает значение сохраненного итератора. Точное поведение определяется тем, является ли операция предекрементной или постдекрементной.|
|[move_iterator::оператор-&gt;](#op_arrow)|Возвращает `&**this`.|
|[move_iterator::оператор-](#operator-)|Возвращает `move_iterator(*this) -=` путем вычитания правого значения из текущей позиции.|
|[move_iterator::operator[]](#op_at)|Возвращает `(reference)*(*this + off)`. Позволяет указать смещение с текущей базы для получения значения в этом местоположении.|
|[move_iterator::оператор](#op_add)|Возвращает `move_iterator(*this) +=` значение. Позволяет добавить смещение в текущую базу для получения значения в этом местоположении.|
|[move_iterator:оператор](#op_add_eq)|Добавляет правое значение к сохраненному итератору и возвращает `*this`.|
|[move_iterator:оператор-я](#operator-_eq)|Вычитает правое значение из сохраненного итератора и возвращает `*this`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="move_iteratorbase"></a><a name="base"></a>move_iterator::база

Возвращает сохраненный итератор для этого `move_iterator`.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Remarks

Эта функция-член возвращает сохраненный итератор.

## <a name="move_iteratordifference_type"></a><a name="difference_type"></a>move_iterator::difference

Тип `difference_type` является `move_iterator` `typedef` на основе признака итератора `difference_type` и взаимозаменяем с ним.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Remarks

Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::pointer`.

## <a name="move_iteratoriterator_category"></a><a name="iterator_category"></a>move_iterator::iterator_category

Тип `iterator_category` является `move_iterator` `typedef` на основе признака итератора `iterator_category` и взаимозаменяем с ним.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Remarks

Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::iterator_category`.

## <a name="move_iteratoriterator_type"></a><a name="iterator_type"></a>move_iterator::iterator_type

Тип `iterator_type` основан на параметре шаблона `RandomIterator` для шаблона класса `move_iterator` и может использоваться вместо него.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `RandomIterator`.

## <a name="move_iteratormove_iterator"></a><a name="move_iterator"></a>move_iterator::move_iterator

Создает итератор перемещения. Использует параметр в качестве сохраненного итератора.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Итератор, который требуется использовать в качестве сохраненного итератора.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует сохраненный итератор с помощью его конструктора по умолчанию. Остальные конструкторы инициализируют сохраненный итератор с использованием `base.base()`.

## <a name="move_iteratoroperator"></a><a name="op_add_eq"></a>move_iterator:оператор

Добавляет смещение к сохраненному итератору, чтобы он указывал на данный элемент в новом текущем расположении. Затем оператор перемещает новый текущий элемент.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Параметры

*_off*\
Смещение, добавляемое к текущей позиции, для определения новой текущей позиции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новый текущий элемент.

### <a name="remarks"></a>Remarks

Оператор добавляет *_Off* к хранимому итератору. Затем возвращает `*this`.

## <a name="move_iteratoroperator-"></a><a name="operator-_eq"></a>move_iterator:оператор-я

Выполняет переход через заданное число предыдущих элементов. Этот оператор вычитает смещение из сохраненного итератора.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Оператор вычисляет `*this += -_Off`. Затем возвращает `*this`.

## <a name="move_iteratoroperator"></a><a name="op_add_add"></a>move_iterator::оператор

Увеличивает сохраненный итератор, который принадлежит `move_iterator.`. Доступ к текущему элементу осуществляется постфиксным оператором. Доступ к следующему элементу осуществляется префиксным оператором.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Первый (префиксный) оператор увеличивает сохраненный итератор. Затем возвращает `*this`.

Второй (постфиксный) оператор создает копию `*this` и вычисляет `++*this`. Затем возвращает эту копию.

## <a name="move_iteratoroperator"></a><a name="op_add"></a>move_iterator::оператор

Возвращает позицию итератора, увеличенную на любое число элементов.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Оператор возвращается `move_iterator(*this) +=` `_Off`.

## <a name="move_iteratoroperator"></a><a name="op_at"></a>move_iterator:оператор

Разрешает доступ индексу массива к элементам во всем диапазоне `move iterator`.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Оператор возвращает `(reference)*(*this + _Off)`.

## <a name="move_iteratoroperator--"></a><a name="operator--"></a>move_iterator:оператор--

Предекрементные и постдекрементные операторы-члены уменьшают сохраненный итератор на единицу.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Первый оператор-член (предекрементный) уменьшает сохраненный итератор. Затем возвращает `*this`.

Второй (постдекрементный) оператор создает копию `*this` и вычисляет `--*this`. Затем возвращает эту копию.

## <a name="move_iteratoroperator-"></a><a name="operator-"></a>move_iterator::оператор-

Уменьшает значение сохраненного итератора и возвращает указанное значение.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Параметры

### <a name="remarks"></a>Remarks

Оператор возвращает `move_iterator(*this) -= _Off`.

## <a name="move_iteratoroperator"></a><a name="op_star"></a>move_iterator:оператор

Разыменовывает сохраненный итератор и возвращает значение. Оператор похож на `rvalue reference` и выполняет присваивание с перемещением. Оператор передает текущий элемент из базового итератора. Следующий элемент становится текущим.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Remarks

Оператор возвращает `(reference)*base()`.

## <a name="move_iteratoroperator-gt"></a><a name="op_arrow"></a>move_iterator::оператор-&gt;

Как обычно, `RandomIterator` `operator->`он обеспечивает доступ к полям, которые принадлежат к текущему элементу.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Remarks

Оператор возвращает `&**this`.

## <a name="move_iteratorpointer"></a><a name="pointer"></a>move_iterator::pointer

Тип `pointer` **typedef** основан на случайном итераторе `RandomIterator` для, `move_iterator`и может быть использован взаимозаменяемо.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Remarks

Тип является синонимом `RandomIterator`.

## <a name="move_iteratorreference"></a><a name="reference"></a>move_iterator::reference

Тип `reference` **typedef** основанный `value_type&&` на, `move_iterator`и может быть использован `value_type&&`взаимозаменяемо с .

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом `value_type&&`, который представляет собой ссылку rvalue.

## <a name="move_iteratorvalue_type"></a><a name="value_type"></a>move_iterator::value_type

Тип `value_type` является `move_iterator` `typedef` на основе признака итератора `value_type` и взаимозаменяем с ним.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Remarks

Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::value_type`.

## <a name="see-also"></a>См. также раздел

[\<итератор>](../standard-library/iterator.md)\
[Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)\
[Перемещение конструкторов и перемещение операторов назначения (СЗ)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)\
[Стандартная библиотечная справка по СЗ](../standard-library/cpp-standard-library-reference.md)
