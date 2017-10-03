---
title: "Операторы &lt;thread&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ff0fa361845c7bf64dd15bfc4e23be7b92b6cc39
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ltthreadgt-operators"></a>Операторы &lt;thread&gt;
||||  
|-|-|-|  
|[operator!=](#op_neq)|[оператор&gt;](#op_gt)|[оператор&gt;=](#op_gt_eq)|  
|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[оператор&lt;=](#op_lt_eq)|  
|[operator==](#op_eq_eq)|  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
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
  
##  <a name="op_gt"></a>  operator&gt;  
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
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
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
  
##  <a name="op_eq_eq"></a>  operator==  
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
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
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




