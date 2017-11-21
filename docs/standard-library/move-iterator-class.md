---
title: "Класс move_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
dev_langs: C++
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
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 59ad715516adfa716a307e1a4e0b7e4cf39e154a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="moveiterator-class"></a>Класс move_iterator
Шаблон класса `move_iterator` является программой-оболочкой для итератора. Move_iterator предоставляет то же поведение, что и инкапсулируемый в него (хранящийся в нем) итератор, за исключением того, что оператор разыменования хранящегося итератора превращается в ссылку rvalue, что превращает копирование в перемещение. Дополнительные сведения о rvalues см. в разделе [Оператор объявления ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="syntax"></a>Синтаксис  
```
class move_iterator;  
```
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает объект, поведение которого аналогично поведению итератора, кроме случаев, когда удаляется ссылка. Он хранит итератор произвольного доступа типа `Iterator`, доступный посредством функции-члена `base()`. Все операции с итератором `move_iterator` выполняются непосредственно в сохраненном итераторе, за исключением того, что результат `operator*` явным образом приводится к `value_type&&` для создания ссылки rvalue.  
  
 Итератор `move_iterator` может выполнять операции, не определенные инкапсулированным итератором. Эти операции не следует использовать.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[move_iterator](#move_iterator)|Конструктор для объектов типа `move_iterator`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[iterator_type](#iterator_type)|Синоним параметра шаблона `RandomIterator`.|  
|[iterator_category](#iterator_category)|Синоним более длинного выражения `typename` с таким же именем, `iterator_category` определяет общие возможности данного итератора.|  
|[value_type](#value_type)|Синоним более длинного выражения `typename` с таким же именем, `value_type` описывает тип элементов итератора.|  
|[difference_type](#difference_type)|Синоним более длинного выражения `typename` с таким же именем, `difference_type` описывает целочисленный тип, необходимый для выражения разницы между элементами.|  
|[pointer](#pointer)|Синоним параметра шаблона `RandomIterator`.|  
|[reference](#reference)|Синоним ссылки `rvalue` `value_type&&`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[base](#base)|Функция-член возвращает сохраненный итератор, инкапсулированный данным итератором `move_iterator`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[move_iterator::operator*](#op_star)|Возвращает `(reference)*base().`.|  
|[move_iterator::operator++](#op_add_add)|Увеличивает значение сохраненного итератора. Точное поведение определяется тем, является ли операция преинкрементной или постинкрементной.|  
|[move_iterator::operator--](#operator--)|Уменьшает значение сохраненного итератора. Точное поведение определяется тем, является ли операция предекрементной или постдекрементной.|  
|[move_iterator::operator-&gt;](#operator-_gt)|Возвращает `&**this`.|  
|[move_iterator::operator-](#operator-)|Возвращает `move_iterator(*this) -=` путем вычитания правого значения из текущей позиции.|  
|[move_iterator::operator[]](#op_at)|Возвращает `(reference)*(*this + off)`. Позволяет указать смещение с текущей базы для получения значения в этом местоположении.|  
|[move_iterator::operator+](#op_add)|Возвращает `move_iterator(*this) +=` значение. Позволяет добавить смещение в текущую базу для получения значения в этом местоположении.|  
|[move_iterator::operator+=](#op_add_eq)|Добавляет правое значение к сохраненному итератору и возвращает `*this`.|  
|[move_iterator::operator-=](#operator-_eq)|Вычитает правое значение из сохраненного итератора и возвращает `*this`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
##  <a name="base"></a>  move_iterator::base  
 Возвращает сохраненный итератор для этого `move_iterator`.  
  
```
RandomIterator base() const;
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает сохраненный итератор.  
  
##  <a name="difference_type"></a>  move_iterator::difference_type  
 Тип `difference_type` является `move_iterator` `typedef` на основе признака итератора `difference_type` и может использоваться с ним взаимозаменяемым образом.  
  
```
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```    
  
### <a name="remarks"></a>Примечания  
 Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::pointer`.  
  
##  <a name="iterator_category"></a>  move_iterator::iterator_category  
 Тип `iterator_category` является `move_iterator` `typedef` на основе признака итератора `iterator_category` и может использоваться с ним взаимозаменяемым образом.  
  
```
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```    
  
### <a name="remarks"></a>Примечания  
 Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::iterator_category`.  
  
##  <a name="iterator_type"></a>  move_iterator::iterator_type  
 Тип `iterator_type` основан на параметре шаблона `RandomIterator` для шаблона класса `move_iterator` и может использоваться вместо него.  
  
```
typedef RandomIterator iterator_type;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `RandomIterator`.  
  
##  <a name="move_iterator"></a>  move_iterator::move_iterator  
 Создает итератор перемещения. Использует параметр в качестве сохраненного итератора.  
  
```
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Итератор, который требуется использовать в качестве сохраненного итератора.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует сохраненный итератор с помощью его конструктора по умолчанию. Остальные конструкторы инициализируют сохраненный итератор с использованием `base.base()`.  
  
##  <a name="op_add_eq"></a>  move_iterator::operator+=  
 Добавляет смещение к сохраненному итератору, чтобы он указывал на данный элемент в новом текущем расположении. Затем оператор перемещает новый текущий элемент.  
  
```
move_iterator& operator+=(difference_type _Off);
```  
  
### <a name="parameters"></a>Параметры  
 `_Off`  
 Смещение, добавляемое к текущей позиции, для определения новой текущей позиции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новый текущий элемент.  
  
### <a name="remarks"></a>Примечания  
 Оператор добавляет `_Off` к сохраненному итератору. Затем возвращает `*this`.  
  
##  <a name="move_iterator__operator-_eq"></a>  move_iterator::operator-=  
 Выполняет переход через заданное число предыдущих элементов. Этот оператор вычитает смещение из сохраненного итератора.  
  
```
move_iterator& operator-=(difference_type _Off);
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Оператор вычисляет `*this += -_Off`. Затем возвращает `*this`.  
  
##  <a name="op_add_add"></a>  move_iterator::operator++  
 Увеличивает сохраненный итератор, который принадлежит `move_iterator.`. Доступ к текущему элементу осуществляется постфиксным оператором. Доступ к следующему элементу осуществляется префиксным оператором.  
  
```
move_iterator& operator++();
move_iterator operator++(int);
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Первый (префиксный) оператор увеличивает сохраненный итератор. Затем возвращает `*this`.  
  
 Второй (постфиксный) оператор создает копию `*this` и вычисляет `++*this`. Затем возвращает эту копию.  
  
##  <a name="op_add"></a>  move_iterator::operator+  
 Возвращает позицию итератора, увеличенную на любое число элементов.  
  
```
move_iterator operator+(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает `move_iterator(*this) +=` `_Off`.  
  
##  <a name="op_at"></a>  move_iterator::operator[]  
 Разрешает доступ индексу массива к элементам во всем диапазоне `move iterator`.  
  
```
reference operator[](difference_type _Off) const;
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает `(reference)*(*this + _Off)`.  
  
##  <a name="move_iterator__operator--"></a>  move_iterator::operator--  
 Предекрементные и постдекрементные операторы-члены уменьшают сохраненный итератор на единицу.  
  
```
move_iterator& operator--();
move_iterator operator--();
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Первый оператор-член (предекрементный) уменьшает сохраненный итератор. Затем возвращает `*this`.  
  
 Второй (постдекрементный) оператор создает копию `*this` и вычисляет `--*this`. Затем возвращает эту копию.  
  
##  <a name="move_iterator__operator-"></a>  move_iterator::operator-  
 Уменьшает значение сохраненного итератора и возвращает указанное значение.  
  
```
move_iterator operator-(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает `move_iterator(*this) -= _Off`.  
  
##  <a name="op_star"></a>  move_iterator::operator*  
 Разыменовывает сохраненный итератор и возвращает значение. Оператор похож на `rvalue reference` и выполняет присваивание с перемещением. Оператор передает текущий элемент из базового итератора. Следующий элемент становится текущим.  
  
```
reference operator*() const;
```  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает `(reference)*base()`.  
  
##  <a name="move_iterator__operator-_gt"></a>  move_iterator::operator-&gt;  
 Как и обычный `RandomIterator` `operator->`, он предоставляет доступ к полям, которые относятся к текущему элементу.  
  
```
pointer operator->() const;
```  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает `&**this`.  
  
##  <a name="pointer"></a>  move_iterator::pointer  
 Тип `pointer` — это `typedef`, основанный на произвольном итераторе `RandomIterator` для `move_iterator`, и может использоваться с ним взаимозаменяемым образом.  
  
```
typedef RandomIterator  pointer;
```    
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом `RandomIterator`.  
  
##  <a name="reference"></a>  move_iterator::reference  
 Тип `reference` — `typedef` на основе `value_type&&` для `move_iterator`, его можно использовать вместо `value_type&&`.  
  
```
typedef value_type&& reference;
```    
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом `value_type&&`, который представляет собой ссылку rvalue.  
  
##  <a name="value_type"></a>  move_iterator::value_type  
 Тип `value_type` является `move_iterator` `typedef` на основе признака итератора `value_type` и может использоваться с ним взаимозаменяемым образом.  
  
```
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```    
  
### <a name="remarks"></a>Примечания  
 Этот тип — синоним для признака итератора `typename iterator_traits<RandomIterator>::value_type`.  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [Конструкторы перемещения и операторы присваивания перемещением (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




