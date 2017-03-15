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
- ppl/concurrency::combinable
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 4ed3ce3d441566a0fb301d01123335846d86a8af
ms.lasthandoff: 02/24/2017

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
|[Конструктор класса combinable](#ctor)|Перегружен. Создает новый `combinable` объекта.|  
|[~ combinable деструктор](#dtor)|Уничтожает объект `combinable`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Clear-метод](#clear)|Очищает все промежуточные вычислительные результаты из предыдущего использования.|  
|[Combine-метод](#combine)|Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор.|  
|[combine_each метод](#combine_each)|Вычисляет окончательное значение из набора вложенных вычислений локального потока, вызывая предоставленный функтор каждый вложенный вычисление локального потока. Конечный результат накапливаются объектом функции.|  
|[Local-метод](#local)|Перегружен. Возвращает ссылку на вложенные вычисления частного потока.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор =-оператор](#operator_eq)|Назначает `combinable` из другого объекта `combinable` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `combinable`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Очистка 

 Очищает все промежуточные вычислительные результаты из предыдущего использования.  
  
```
void clear();
```  
  
##  <a name="a-namectora-combinable"></a><a name="ctor"></a>combinable 

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
  
##  <a name="a-namedtora-combinable"></a><a name="dtor"></a>~ combinable 

 Уничтожает объект `combinable`.  
  
```
~combinable();
```  
  
##  <a name="a-namecombinea-combine"></a><a name="combine"></a>Объединение 

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
  
##  <a name="a-namecombineeacha-combineeach"></a><a name="combine_each"></a>combine_each 

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
  
##  <a name="a-namelocala-local"></a><a name="local"></a>локальный 

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
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

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
 [пространство имен Concurrency](concurrency-namespace.md)

