---
title: "Класс index | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d227876285de1ea0784ac28b7a772ef35b6a9c49
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="index-class"></a>Класс index
Определяет *N*-pographics-cpp-amp.md измерений индекса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>Параметры  
 `_Rank`  
 Ранг или число измерений.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Индекс конструктора](#ctor)|Инициализирует новый экземпляр класса `index`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор--](#operator--)|Уменьшает значение каждого элемента `index` объекта.|  
|[operator(mod)=](#operator_mod_eq)|Вычисляет модуль (остаток от деления) каждого элемента в `index` объекта при делении на ряд этого элемента.|  
|[оператор*=](#operator_star_eq)|Умножает каждый элемент `index` объекта по номеру.|  
|[оператор/=](#operator_div_eq)|Делит каждый элемент `index` объекта по номеру.|  
|[index::operator\[\]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|  
|[оператор++](#operator_add_add)|Увеличивает значение каждого элемента `index` объекта.|  
|[оператор+=](#operator_add_eq)|Добавляет указанный номер каждого элемента `index` объекта.|  
|[оператор=](#operator_eq)|Копирует содержимое указанного `index` объекта в другой.|  
|[оператор-=](#operator_-_eq)|Вычитает из каждого элемента заданного числа `index` объекта.|  

  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Ранг константа](#rank)|Сохраняет ранг объекта `index` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `index`  
  
## <a name="remarks"></a>Примечания  
 `index` Структура представляет координат вектора *N* целых чисел, задающий уникальный позицию в *N*-мерном пространстве. Значения в объекте vector упорядочиваются от наиболее важных до наименее важных. Можно извлечь значения компонентов, с помощью [оператор =](#operator_eq).  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  


## <a name="index_ctor">Индекс конструктора</a>
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
Одномерный массив с ранжирующие значения.  
_I  
Индекс в одномерный индекс.  
_I0  
Длина наиболее значимых измерения.  
_I1  
Длина следующего к старший значащий измерения.  
_I2  
Длина младших измерения.  
_Other  
Индекс объекта, на котором основан новый объект индекса.  

## <a name="operator--"></a>  оператор--
Уменьшает значение каждого элемента или объекта индекса.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>Возвращаемые значения
Для оператора префикс объект индекса (* это). Для оператора суффикс новый объект индекса.

## <a name="operator_mod_eq"></a>  Operator(MOD) =   
Вычисляет модуль (остаток от деления) каждого элемента в объект индекса при делении на указанное число этого элемента.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>Параметры
_Rhs число, которое необходимо разделить, чтобы найти остаток.
Возвращаемое значение индекс объекта.

## <a name="operator_star_eq"></a>  оператор * =   
Умножает каждый элемент в объект индекса, заданного числа.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры
_Rhs число для перемножения.

## <a name="operator_div_eq"></a>  оператор / = 
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
Элемент, расположенный по указанному индексу.

### <a name="remarks"></a>Примечания
В следующем примере отображаются значения компонента индекса.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>  Operator ++   
Увеличивает значение каждого элемента или объекта индекса.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>Возвращаемое значение
Для оператора префикс объект индекса (* это). Для оператора суффикс новый объект индекса.

## <a name="operator_add_eq"></a>  оператор +=   
Добавляет указанный номер каждого элемента или объекта индекса.
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
Индекс объекта.

## <a name="operator_eq"></a>  оператор=   
Копирует содержимое объекта указанный индекс в другой.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Параметры
_Other объект для копирования из индекса.

### <a name="return-value"></a>Возвращаемое значение
Ссылка на этот объект индекса.

## <a name="operator_-_eq"></a>  оператор-=
Вычитает из каждого элемента или объекта индекса заданного числа.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>Параметры
_Rhs номер для вычитания.

### <a name="return-value"></a>Возвращаемое значение
Индекс объекта.   

## <a name="rank"></a>  Ранг  
  Возвращает ранг объекта индекса.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
