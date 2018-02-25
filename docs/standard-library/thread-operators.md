---
title: "Операторы &lt;thread&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
dev_langs:
- C++
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: f1a004cca5d43c22b5315c50b61cb0fcafb2cf10
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltthreadgt-operators"></a>Операторы &lt;thread&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|  
|[оператор==](#op_eq_eq)|  
  
##  <a name="op_gt_eq"></a> operator&gt;=  
 Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `!(Left < Right)`  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="op_gt"></a> operator&gt;  
 Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `Right < Left`  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="op_lt_eq"></a> operator&lt;=  
 Определяет, справедливо ли, что один из объектов `thread::id` меньше другого или равен ему.  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `!(Right < Left)`  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="op_lt"></a>  operator&lt;  
 Определяет, справедливо ли, что один объект `thread::id` меньше другого.  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если `Left` предшествует `Right` в общем порядке; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Оператор определяет общий порядок всех объектов `thread::id`. Эти объекты могут использоваться в качестве ключей в ассоциативных контейнерах.  
  
 Эта функция не вызывает исключений.  
  
##  <a name="op_neq"></a>  operator!=  
 Проверяет неравенство двух объектов `thread::id`.  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `!(Left == Right)`  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="op_eq_eq"></a> operator==  
 Сравнивает два объекта `thread::id` на равенство.  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread::id`.  
  
 `Right`  
 Правой объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если два объекта представляют тот же поток выполнения или если ни один из объектов не представляет поток выполнения; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="op_lt_lt"></a> operator&lt;&lt;  
 Вставляет текстовое представление объекта `thread::id` в поток.  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>Параметры  
 `Ostr`  
 Объект [basic_ostream](../standard-library/basic-ostream-class.md).  
  
 `Id`  
 Объект `thread::id`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `Ostr`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вставляет `Id` в `Ostr`.  
  
 Если два объекта `thread::id` равны, вставленные текстовые представления этих объектов совпадают.  
  
## <a name="see-also"></a>См. также  
 [\<thread>](../standard-library/thread.md)



