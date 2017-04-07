---
title: "Класс index | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
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
ms.openlocfilehash: 52c19da3cb8de10c3963ca3b795cac1babb3dc7a
ms.lasthandoff: 03/17/2017

---
# <a name="index-class"></a>Класс index
Определяет *N*-pographics-cpp-amp.md индекса размерности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг или число измерений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Индекс конструктора](#ctor)|Инициализирует новый экземпляр класса `index`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор--](#operator--)|Уменьшает значение каждого элемента `index` объекта.|  
|[Operator(MOD) =](#operator_mod_eq)|Вычисляет остаток (остаток от деления) каждого элемента в `index` объекта при делении на номер элемента.|  
|[оператор*=](#operator_star_eq)|Умножает каждый элемент `index` объекта числом.|  
|[оператор/=](#operator_div_eq)|Делит каждый элемент `index` объекта числом.|  
|[index::operator\[\]](#operator_at)|Возвращает элемент, который находится по указанному индексу.|  
|[оператор++](#operator_add_add)|Увеличивает значение каждого элемента `index` объекта.|  
|[оператор+=](#operator_add_eq)|Добавляет указанный номер каждого элемента `index` объекта.|  
|[operator=](#operator_eq)|Копирует содержимое указанного `index` объекта в другой.|  
|[оператор-=](#operator_-_eq)|Вычитает из каждого элемента заданного числа `index` объекта.|  

  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Сохраняет ранг объекта `index` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `index`  
  
## <a name="remarks"></a>Примечания  
 `index` Структуры представляет собой координат вектор *N* целых чисел, указывающий уникальное положение в *N*-двухмерном пространстве. Значения в объекте vector упорядочиваются от наиболее важных до наименее важных. Можно извлечь значения компоненты с помощью [оператор =](#operator_eq).  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  


## <a name="index_ctor"></a>Индекс конструктора
Инициализирует новый экземпляр класса индекса.

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>Параметры

_Array  
Одномерный массив с рангом.  
_УСЛОВИЯ  
Индекс в одномерный индекс.  
_I0  
Длина наиболее значимых измерения.  
_I1  
Длина следующего к значащий измерения.  
_I2  
Длина младших измерения.  
_Other  
Индекс объекта, на котором основан новый объект индекса.  

## <a name="operator--"></a>оператор--
Уменьшает на единицу каждый элемент объекта индекса.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>Возвращаемые значения
Для оператора префикс объект индекса (* это). Для оператора суффикс новый объект индекса.

## <a name="operator_mod_eq"></a>Operator(MOD) =   
Вычисляет остаток (остаток от деления) каждого элемента в объекте индекса при делении на указанное число этого элемента.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>Параметры
_Rhs число-знаменатель, чтобы найти остаток.
Возвращаемое значение индекса объекта.

## <a name="operator_star_eq"></a>оператор * =   
Умножает каждый элемент в объект индекса на указанное число.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры
_Rhs число для перемножения.

## <a name="operator_div_eq"></a>оператор / = 
Делит каждый элемент в объект индекса заданного числа.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Параметры
_Rhs число-знаменатель.

## <a name="operator_at"></a> operator\[\]  
Возвращает компонент в указанном расположении индекса.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры
_Index целое число от 0 до ранг минус 1.

### <a name="return-value"></a>Возвращаемое значение
Элемент, который находится по указанному индексу.

### <a name="remarks"></a>Примечания
В следующем примере отображаются значения компонента индекса.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>Operator ++   
Увеличивает значение каждого элемента объекта индекса.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>Возвращаемое значение
Для оператора префикс объект индекса (* это). Для оператора суффикс новый объект индекса.

## <a name="operator_add_eq"></a>оператор +=   
Добавляет заданное число для каждого элемента объекта индекса.
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Параметры
_Rhs число для сложения.

### <a name="return-value"></a>Возвращаемое значение
Объект индекса.

## <a name="operator_eq"></a>  оператор=   
Копирует содержимое объекта указанного индекса в другой.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Параметры
Объект индекса для копирования из _Other.

### <a name="return-value"></a>Возвращаемое значение
Ссылка на этот объект индекса.

## <a name="operator_-_eq"></a>оператор-=
Вычитает указанный номер из каждого элемента объекта индекса.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>Параметры
_Rhs числа для вычитания.

### <a name="return-value"></a>Возвращаемое значение
Объект индекса.   

## <a name="rank"></a>Ранг  
  Возвращает ранг объекта индекса.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

