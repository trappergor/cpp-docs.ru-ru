---
title: "область класса (C++ AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 28c90118eeb83df75f19b49f47ac884bff111b8f
ms.lasthandoff: 03/17/2017

---
# <a name="extent-class-c-amp"></a>Касс extent (C++ AMP)
Представляет собой вектор *N* целочисленных значений, указывающих границы *N*-двухмерном пространстве, который соответствует значение 0. Значения в объекте vector упорядочиваются от наиболее важных до наименее важных.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг `extent` объекта.  

 ## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[область конструктора](#ctor)|Инициализирует новый экземпляр класса `extent`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[содержит](#contains)|Проверяет, что указанный `extent` объект с указанным рангом.|  
|[size](#size)|Возвращает общий размер линейной области памяти (в единицах элементов).|  
|[Плитка](#tile)|Создает `tiled_extent` плитки экстентов, предоставленных указанным измерений.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор-](#operator_min)|Возвращает новый `extent` объекта, созданного путем вычитания `index` элементы из соответствующего `extent` элементы.|  
|[оператор--](#operator_min_min)|Уменьшает значение каждого элемента `extent` объекта.|  
|[оператор%=](#operator_mod_eq)|Вычисляет остаток (остаток от деления) каждого элемента в `extent` объекта при делении на номер элемента.|  
|[оператор*=](#operator_star_eq)|Умножает каждый элемент `extent` объекта числом.|  
|[оператор/=](#operator_min_eq)|Делит каждый элемент `extent` объекта числом.|  
|[Extent::operator\[\]](#operator_at)|Возвращает элемент, который находится по указанному индексу.|  
|[operator+](#operator_add)|Возвращает новый `extent` объект, который создается путем добавления соответствующего `index` и `extent` элементы.|  
|[оператор++](#operator_add_add)|Увеличивает значение каждого элемента `extent` объекта.|  
|[оператор+=](#operator_add_eq)|Добавляет указанный номер каждого элемента `extent` объекта.|  
|[operator=](#operator_eq)|Копирует содержимое другого `extent` объекта в другой.|  
|[оператор-=](#operator_min_eq)|Вычитает из каждого элемента заданного числа `extent` объекта.|  

  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Возвращает ранг `extent` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `extent`  


## <a name="contains"></a>содержит 

Указывает, является ли указанный [индекс](index-class.md) значение содержится в объекте «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 `index` Значение для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если указанный `index` значение содержится в `extent` объекта; в противном случае — `false`.  
  
##  <a name="ctor"></a>экстент 

Инициализирует новый экземпляр класса «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Array`  
 Массив `_Rank` целых чисел, который используется для создания нового `extent` объекта.  
  
 `_I`  
 Длина экстента.  
  
 `_I0`  
 Длина наиболее значимых измерения.  
  
 `_I1`  
 Длина следующего к значащий измерения.  
  
 `_I2`  
 Длина младших измерения.  
  
 `_Other`  
 `extent` Объект, на котором новый `extent` основан объект.  
  
## <a name="remarks"></a>Примечания  
 Этот конструктор инициализирует `extent` объект, который имеет ранг&3;.  
  
 Если массив используется для создания `extent` объекта длина массива должен соответствовать ранг `extent` объекта.  
  
##  <a name="operator_mod_eq"></a>оператор % = 

Вычисляет остаток (остаток от деления) каждого элемента в экстенте при делении на номер элемента.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Номер, чтобы найти остаток от.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `extent`.  
  
##  <a name="operator_star_eq"></a>оператор * = 

Умножает каждый элемент в объекте «область» на указанное число.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Число для перемножения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `extent`.  
  
## <a name="operator_add"></a>оператор + 

Возвращает новый `extent` объект, созданный путем добавления соответствующего `index` и `extent` элементы.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 `index` Объект, содержащий добавляемые элементы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый объект `extent`.  
  
##  <a name="operator_add_add"></a>Operator ++ 

Увеличивает каждый элемент объекта «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для оператора префикс `extent` объекта (`*this`). Для оператора суффикс нового `extent` объекта.  
  
##  <a name="operator_add_eq"></a>оператор += 

Добавляет указанный номер каждый элемент объекта «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Номер индекса или экстент для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующий объект `extent`.  
  
##  <a name="operator_min"></a>оператор- 

Создает новый `extent` объекта путем вычитания каждого элемента в заданном `index` объект из соответствующего элемента в этом `extent` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 `index` Объект, который содержит элементы для вычитания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый объект `extent`.  
  
##  <a name="operator_min_min"></a>оператор-- 

Уменьшает значение каждого элемента в объекте «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Для оператора префикс `extent` объекта (`*this`). Для оператора суффикс нового `extent` объекта.  
  
##  <a name="operator_div_eq"></a>оператор / = 

Делит каждый элемент в объекте «область» указанного числа.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Число-знаменатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `extent`.  
  
##  <a name="operator_min_eq"></a>оператор-= 

Вычитает указанный номер из каждого элемента объекта «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Номер для вычитания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующий объект `extent`.  
  
##  <a name="operator_eq"></a>оператор = 

Копирует содержимое другого объекта «область» в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `extent` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `extent` объекта.  
  
##  <a name="operator_at"></a>Extent::operator\[\] 
Возвращает элемент, который находится по указанному индексу.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Целое число от 0 до ранг минус 1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, который находится по указанному индексу.  
  
##  <a name="rank_constant"></a>Ранг 

Сохраняет ранг объекта «область».  
  
### <a name="syntax"></a>Синтаксис  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="size"></a>размер 

Возвращает общий размер линейной `extent` объекта (в единицах элементов).  
  
### <a name="syntax"></a>Синтаксис  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="tile"></a>Плитка 

Создает объект tiled_extent с размерами указанного плитки.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>Параметры
`_Dim0`Наиболее значимые компонент разбитом.
`_Dim1`Далее к значащий компонент разбитом.
`_Dim2`Компонент младших разбитом.


  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

