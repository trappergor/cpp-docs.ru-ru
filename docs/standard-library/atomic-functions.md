---
title: "&lt;Атомарные&gt; функции | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3b10205d490f9ac7a4f69ef01fc0da30fe7012ed
ms.lasthandoff: 02/24/2017

---
# <a name="ltatomicgt-functions"></a>&lt;Атомарные&gt; функции
||||  
|-|-|-|  
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong_function)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit_function)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak_function)|  
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit_function)|[atomic_exchange](#atomic_exchange_function)|[atomic_exchange_explicit](#atomic_exchange_explicit_function)|  
|[atomic_fetch_add](#atomic_fetch_add_function)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit_function)|[atomic_fetch_and](#atomic_fetch_and_function)|  
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit_function)|[atomic_fetch_or](#atomic_fetch_or_function)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit_function)|  
|[atomic_fetch_sub](#atomic_fetch_sub_function)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit_function)|[atomic_fetch_xor](#atomic_fetch_xor_function)|  
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit_function)|[atomic_flag_clear](#atomic_flag_clear_function)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit_function)|  
|[atomic_flag_test_and_set](#atomic_flag_test_and_set_function)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit_function)|[atomic_init](#atomic_init_function)|  
|[atomic_is_lock_free](#atomic_is_lock_free_function)|[atomic_load](#atomic_load_function)|[atomic_load_explicit](#atomic_load_explicit_function)|  
|[atomic_signal_fence](#atomic_signal_fence_function)|[atomic_store](#atomic_store_function)|[atomic_store_explicit](#atomic_store_explicit_function)|  
|[atomic_thread_fence](#atomic_thread_fence_function)|[kill_dependency](#kill_dependency_function)|  
  
##  <a name="a-nameatomiccompareexchangestrongfunctiona--atomiccompareexchangestrong"></a><a name="atomic_compare_exchange_strong_function"></a>  atomic_compare_exchange_strong  
 Выполняет атомарную операцию сравнения и обмена.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Exp`  
 Указатель на значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение `bool`, указывающее результат сравнения значений.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет атомарную операцию сравнения и обмена с помощью неявных аргументов `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit_function).  
  
##  <a name="a-nameatomiccompareexchangestrongexplicitfunctiona--atomiccompareexchangestrongexplicit"></a><a name="atomic_compare_exchange_strong_explicit_function"></a>  atomic_compare_exchange_strong_explicit  
 Выполняет *атомарную операцию сравнения и обмена*.  
  
```
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Exp`  
 Указатель на значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
 `Order1`  
 Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 `Order2`  
 Второй аргумент `memory_order`. Значение `Order2` не может быть `memory_order_release` или `memory_order_acq_rel`, и оно не может быть надежнее, чем значение `Order1`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение `bool`, указывающее результат сравнения значений.  
  
### <a name="remarks"></a>Примечания  
 *Атомарная операция сравнения и обмена* сравнивает значение, хранящееся в объекте, на который указывает `Atom`, со значением, на которое указывает `Exp`. Если значения равны, то значение, хранящееся в объекте, на который указывает `atom`, заменяется на `Val` с помощью операции `read-modify-write` и применения ограничений порядка памяти, которые задаются с помощью `Order1`. Если значения не равны, операция заменяет значение, указанное `Exp`, на значение, хранящееся в объекте, на который указывает `Atom`, и применяет ограничения порядка памяти, которые задаются с помощью `Order2`.  
  
##  <a name="a-nameatomiccompareexchangeweakfunctiona--atomiccompareexchangeweak"></a><a name="atomic_compare_exchange_weak_function"></a>  atomic_compare_exchange_weak  
 Выполняет *слабую атомарную операцию сравнения и обмена*.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Exp`  
 Указатель на значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение `bool`, указывающее результат сравнения значений.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет *слабую атомарную операцию сравнения и обмена* с помощью неявных аргументов `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit_function).  
  
##  <a name="a-nameatomiccompareexchangeweakexplicitfunctiona--atomiccompareexchangeweakexplicit"></a><a name="atomic_compare_exchange_weak_explicit_function"></a>  atomic_compare_exchange_weak_explicit  
 Выполняет *слабую атомарную операцию сравнения и обмена*.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp, 
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Exp`  
 Указатель на значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
 `Order1`  
 Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 `Order2`  
 Второй аргумент `memory_order`. Значение `Order2` не может быть `memory_order_release` или `memory_order_acq_rel`, и оно не может быть надежнее, чем значение `Order1`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение `bool`, указывающее результат сравнения значений.  
  
### <a name="remarks"></a>Примечания  
 *Атомарная операция сравнения и обмена* сравнивает значение, хранящееся в объекте, на который указывает `Atom`, со значением, указанным `Exp`. Если значения равны, то операция заменяет значение, хранящееся в объекте, на который указывает `Atom`, на `Val` с помощью операции `read-modify-write` и применения ограничений порядка памяти, которые задаются с помощью `Order1`. Если значения не равны, операция заменяет значение, указанное `Exp`, на значение, хранящееся в объекте, на который указывает `Atom`, и применяет ограничения порядка памяти, которые задаются с помощью `Order2`.  
  
 *Слабая* атомарная операция сравнения и обмена выполняет обмен, если сравниваемые значения равны. Однако если значения не равны, операция необязательно выполнит обмен.  
  
##  <a name="a-nameatomicexchangefunctiona--atomicexchange"></a><a name="atomic_exchange_function"></a>  atomic_exchange  
 Использует `Value` для замены сохраненного значения `Atom`.  
  
```
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сохраненное значение `Atom` до обмена.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_exchange` выполняет операцию `read-modify-write` для обмена значения, которое хранится в `Atom`, на `Value`, используя `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicexchangeexplicitfunctiona--atomicexchangeexplicit"></a><a name="atomic_exchange_explicit_function"></a>  atomic_exchange_explicit  
 Заменяет значение, хранящееся в `Atom`, на `Value`.  
  
```
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сохраненное значение `Atom` до обмена.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_exchange_explicit` выполняет операцию `read-modify-write` для обмена значения, которое хранится в `Atom`, на `Value` с соблюдением ограничений памяти, которые задаются с помощью `Order`.  
  
##  <a name="a-nameatomicfetchaddfunctiona--atomicfetchadd"></a><a name="atomic_fetch_add_function"></a>  atomic_fetch_add  
 Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.  
  
```
template <class T>  
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>  
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит указатель на тип `T`.  
  
 `Value`  
 Значение типа `ptrdiff_t`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_add` выполняет операцию `read-modify-write`, чтобы атомарным образом добавить `Value` к значению, хранящемуся в `Atom`, используя ограничение `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.  
  
 Эта операция также перегружается для целочисленных типов:  
  
```
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="a-nameatomicfetchaddexplicitfunctiona--atomicfetchaddexplicit"></a><a name="atomic_fetch_add_explicit_function"></a>  atomic_fetch_add_explicit  
 Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.  
  
```
template <class T>  
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom, 
    ptrdiff_t Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит указатель на тип `T`.  
  
 `Value`  
 Значение типа `ptrdiff_t`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_add_explicit` выполняет операцию `read-modify-write`, чтобы атомарным образом добавить `Value` к сохраненному значению в `Atom` с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum)`Order`.  
  
 Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.  
  
 Эта операция также перегружается для целочисленных типов:  
  
```cpp  
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="a-nameatomicfetchandfunctiona--atomicfetchand"></a><a name="atomic_fetch_and_function"></a>  atomic_fetch_and  
 Выполняет побитовую операцию `and` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_and` выполняет операцию `read-modify-write`, чтобы заменить значение, хранящееся в `Atom`, на результат побитовой операции `and` с `Value` и текущим значением, хранящимся в `Atom`, с использованием ограничения `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchandexplicitfunctiona--atomicfetchandexplicit"></a><a name="atomic_fetch_and_explicit_function"></a>  atomic_fetch_and_explicit  
 Выполняет побитовую операцию `and` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
    
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_and_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `and` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений, заданных с помощью `Order`.  
  
##  <a name="a-nameatomicfetchorfunctiona--atomicfetchor"></a><a name="atomic_fetch_or_function"></a>  atomic_fetch_or  
 Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_or` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `or` с `Value` и текущим значением, хранящимся в `Atom`, с использованием `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchorexplicitfunctiona--atomicfetchorexplicit"></a><a name="atomic_fetch_or_explicit_function"></a>  atomic_fetch_or_explicit  
 Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_or_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `or` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.  
  
##  <a name="a-nameatomicfetchsubfunctiona--atomicfetchsub"></a><a name="atomic_fetch_sub_function"></a>  atomic_fetch_sub  
 Вычитает значение из существующего значения, хранящегося в объекте `atomic`.  
  
```
template <class T>  
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>  
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит указатель на тип `T`.  
  
 `Value`  
 Значение типа `ptrdiff_t`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_sub` выполняет операцию `read-modify-write`, чтобы атомарным образом вычесть `Value` из значения, хранящегося в `Atom`, используя ограничение `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.  
  
 Эта операция также перегружается для целочисленных типов:  
  
```
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="a-nameatomicfetchsubexplicitfunctiona--atomicfetchsubexplicit"></a><a name="atomic_fetch_sub_explicit_function"></a>  atomic_fetch_sub_explicit  
 Вычитает значение из существующего значения, хранящегося в объекте `atomic`.  
  
```
template <class T>  
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит указатель на тип `T`.  
  
 `Value`  
 Значение типа `ptrdiff_t`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_sub_explicit` выполняет операцию `read-modify-write`, чтобы атомарным образом вычесть `Value` из значения, хранящегося в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.  
  
 Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.  
  
 Эта операция также перегружается для целочисленных типов:  
  
```cpp  
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="a-nameatomicfetchxorfunctiona--atomicfetchxor"></a><a name="atomic_fetch_xor_function"></a>  atomic_fetch_xor  
 Выполняет побитовую операцию `exclusive or` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept; 

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_xor` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `exclusive or` с `Value` и текущим значением, хранящимся в `Atom`, с использованием `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchxorexplicitfunctiona--atomicfetchxorexplicit"></a><a name="atomic_fetch_xor_explicit_function"></a>  atomic_fetch_xor_explicit  
 Выполняет побитовую операцию `exclusive or` со значением и существующим значением, хранящимся в объекте `atomic`.  
  
```
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
 `Value`  
 Значение типа `T`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.  
  
### <a name="remarks"></a>Примечания  
 Функция `atomic_fetch_xor_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `exclusive or` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.  
  
##  <a name="a-nameatomicflagclearfunctiona--atomicflagclear"></a><a name="atomic_flag_clear_function"></a>  atomic_flag_clear  
 Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `false` с соблюдением ограничений `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Flag`  
 Указатель на объект `atomic_flag`.  
  
##  <a name="a-nameatomicflagclearexplicitfunctiona--atomicflagclearexplicit"></a><a name="atomic_flag_clear_explicit_function"></a>  atomic_flag_clear_explicit  
 Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `false` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Flag`  
 Указатель на объект `atomic_flag`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicflagtestandsetfunctiona--atomicflagtestandset"></a><a name="atomic_flag_test_and_set_function"></a>  atomic_flag_test_and_set  
 Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `true` с соблюдением ограничений `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Flag`  
 Указатель на объект `atomic_flag`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальное значение `Flag`.  
  
##  <a name="a-nameatomicflagtestandsetexplicitfunctiona--atomicflagtestandsetexplicit"></a><a name="atomic_flag_test_and_set_explicit_function"></a>  atomic_flag_test_and_set_explicit  
 Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `true` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Flag`  
 Указатель на объект `atomic_flag`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальное значение `Flag`.  
  
##  <a name="a-nameatomicinitfunctiona--atomicinit"></a><a name="atomic_init_function"></a>  atomic_init  
 Задает сохраненное значение в объекте `atomic`.  
  
```
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
### <a name="remarks"></a>Примечания  
 `atomic_init` не является атомарной операцией. Этот указатель не является потокобезопасным.  
  
##  <a name="a-nameatomicislockfreefunctiona--atomicislockfree"></a><a name="atomic_is_lock_free_function"></a>  atomic_is_lock_free  
 Указывает, являются ли операции с объектом `atomic` *неблокирующими*.  
  
```
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который хранит значение типа `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если атомарные операции с `Atom` являются неблокирующими; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Атомарный тип является неблокирующим, если никакие атомарные операции с этим типом не используют блокировки. Если эта функция возвращает значение true, тип можно безопасно использовать в обработчиках сигналов.  
  
##  <a name="a-nameatomicloadfunctiona--atomicload"></a><a name="atomic_load_function"></a>  atomic_load  
 Извлекает сохраненное значение в объект `atomic`.  
  
```
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который содержит значение типа `Ty`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлеченное значение, которое хранится в `Atom`.  
  
### <a name="remarks"></a>Примечания  
 `atomic_load`неявно использует `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicloadexplicitfunctiona--atomicloadexplicit"></a><a name="atomic_load_explicit_function"></a>  atomic_load_explicit  
 Извлекает сохраненное значение в объект `atomic` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который содержит значение типа `Ty`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_release``memory_order_acq_rel`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлеченное значение, которое хранится в `Atom`.  
  
##  <a name="a-nameatomicsignalfencefunctiona--atomicsignalfence"></a><a name="atomic_signal_fence_function"></a>  atomic_signal_fence  
 Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — между другими границами в вызывающем потоке, которые имеют обработчики сигнала, выполняющиеся в одном потоке.  
  
```
inline void atomic_signal_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Order`  
 Ограничение порядка памяти, которое определяет тип границы.  
  
### <a name="remarks"></a>Примечания  
 Аргумент `Order` определяет тип границы.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Граница не действует.|  
|`memory_order_consume`|Граница является границей получения.|  
|`memory_order_acquire`|Граница является границей получения.|  
|`memory_order_release`|Граница является границей выпуска.|  
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|  
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|  
  
##  <a name="a-nameatomicstorefunctiona--atomicstore"></a><a name="atomic_store_function"></a>  atomic_store  
 Атомарным образом сохраняет значение в атомарном объекте.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на атомарный объект, который содержит значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
### <a name="remarks"></a>Примечания  
 `atomic_store` хранит `Value` в объекте, указанном `Atom`, с соблюдением ограничения `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicstoreexplicitfunctiona--atomicstoreexplicit"></a><a name="atomic_store_explicit_function"></a>  atomic_store_explicit  
 Атомарным образом сохраняет значение в атомарном объекте.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom, 
    Ty Value, 
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom, 
    T Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Atom`  
 Указатель на объект `atomic`, который содержит значение типа `Ty`.  
  
 `Value`  
 Значение типа `Ty`.  
  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_consume`, `memory_order_acquire` или `memory_order_acq_rel`.  
  
### <a name="remarks"></a>Примечания  
 `atomic_store` хранит `Value` в объекте, указанном `Atom`, с соблюдением ограничений `memory_order`, заданных с помощью `Order`.  
  
##  <a name="a-nameatomicthreadfencefunctiona--atomicthreadfence"></a><a name="atomic_thread_fence_function"></a>  atomic_thread_fence  
 Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — без связанной атомарной операции.  
  
```
inline void atomic_thread_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Order`  
 Ограничение порядка памяти, которое определяет тип границы.  
  
### <a name="remarks"></a>Примечания  
 Аргумент `Order` определяет тип границы.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Граница не действует.|  
|`memory_order_consume`|Граница является границей получения.|  
|`memory_order_acquire`|Граница является границей получения.|  
|`memory_order_release`|Граница является границей выпуска.|  
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|  
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|  
  
##  <a name="a-namekilldependencyfunctiona--killdependency"></a><a name="kill_dependency_function"></a>  kill_dependency  
 Удаляет зависимость.  
  
```
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Arg`  
 Значение типа `Ty`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение — `Arg`. Вычисление `Arg` не содержит зависимость для вызова функции. Разбивая возможную цепочку зависимостей, функция позволяет компилятору создавать более эффективный код.  
  
## <a name="see-also"></a>См. также  
 [\<atomic>](../standard-library/atomic.md)




