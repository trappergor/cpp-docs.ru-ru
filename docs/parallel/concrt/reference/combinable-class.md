---
title: "Класс combinable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
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
ms.openlocfilehash: a491f8eef59978808608917531a5237cceacdb21
ms.lasthandoff: 03/17/2017

---
# <a name="combinable-class"></a>Класс combinable
Объект `combinable<T>` предназначен для предоставления частной для потока копии данных для выполнения локальных для потока вложенных вычислений без блокировки потока в параллельных алгоритмах. В конце выполнения параллельной операции частные для потока вложенные вычисления можно объединить для получения общего результата. Этот класс можно использовать вместо общей переменной, что может позволить улучшить производительность в случае возникновения большого числа конфликтов доступа к этой общей переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных окончательному результату слияния. Тип должен иметь конструктор копирования и конструктор по умолчанию.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[combinable](#ctor)|Перегружен. Создает новый `combinable` объекта.|  
|[~ combinable деструктор](#dtor)|Уничтожает объект `combinable`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[clear](#clear)|Очищает все промежуточные вычислительные результаты из предыдущего использования.|  
|[combine](#combine)|Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор.|  
|[combine_each](#combine_each)|Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор каждый вложенный вычисление локального потока. Конечный результат накапливаются объектом функции.|  
|[локальный](#local)|Перегружен. Возвращает ссылку на вложенные вычисления частного потока.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator=](#operator_eq)|Назначает `combinable` из другого объекта `combinable` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `combinable`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="clear"></a>Очистка 

 Очищает все промежуточные вычислительные результаты из предыдущего использования.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>combinable 

 Создает новый `combinable` объекта.  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функтора инициализации.  
  
 `_FnInitialize`  
 Функция, которая будет вызываться для инициализации каждого нового потока частного значения типа `T`. Он должен поддерживать оператор вызова функции с сигнатурой `T ()`.  
  
 `_Copy`  
 Существующий `combinable` копируемый в данный объект.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует новые элементы с помощью конструктора по умолчанию для типа `T`.  
  
 Второй конструктор инициализирует новые элементы, используя функтор инициализации, предоставленные в качестве `_FnInitialize` параметр.  
  
 Третий конструктор является конструктор копий.  
  
##  <a name="dtor"></a>~ combinable 

 Уничтожает объект `combinable`.  
  
```
~combinable();
```  
  
##  <a name="combine"></a>Объединение 

 Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор.  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, который будет вызван для объединения двух вложенных вычислений локального потока.  
  
 `_FnCombine`  
 Функтор, который используется для объединения вложенных вычислений. Он имеет сигнатуру `T (T, T)` или `T (const T&, const T&)`, и он должен быть ассоциативными и коммуникативными.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окончательный результат объединения всех вычислений вложенные закрытого потока.  
  
##  <a name="combine_each"></a>combine_each 

 Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор каждый вложенный вычисление локального потока. Конечный результат накапливаются объектом функции.  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, который будет вызван для объединения одного подвычисления локального потока.  
  
 `_FnCombine`  
 Функтор, который используется для объединения одного подвычисления. Он имеет сигнатуру `void (T)` или `void (const T&)`и должен быть ассоциативными и коммуникативными.  
  
##  <a name="local"></a>локальный 

 Возвращает ссылку на вложенные вычисления частного потока.  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>Параметры  
 `_Exists`  
 Ссылка на логическое значение. Будет присвоено логическое значение, которое ссылается данный аргумент `true` подвычисление уже существовало в данном потоке и установите `false` Если это был первый подвычисление в данном потоке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на вложенный вычисления частного потока.  
  
##  <a name="operator_eq"></a>оператор = 

 Назначает `combinable` из другого объекта `combinable` объекта.  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>Параметры  
 `_Copy`  
 Существующий `combinable` копируемый в данный объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `combinable` объекта.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

