---
title: "Операторы &lt;thread&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7e849e8585b372b5b423a6c960aa926ac7d5cfec
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-operators"></a>Операторы &lt;thread&gt;
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[оператор&gt;](#operator_gt_)|[оператор&gt;=](#operator_gt__eq)|  
|[оператор&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[оператор&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
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
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
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
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
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
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
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
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
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
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
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
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
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




