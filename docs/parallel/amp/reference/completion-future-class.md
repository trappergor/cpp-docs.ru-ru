---
title: "Класс completion_future | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
dev_langs:
- C++
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
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
ms.openlocfilehash: 1c6d8e880fbdb784b22b1e9c879473efa7bc9802
ms.lasthandoff: 03/17/2017

---
# <a name="completionfuture-class"></a>Класс completion_future
Представляет будущих соответствующий асинхронную операцию C++ AMP.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class completion_future;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор completion_future](#ctor)|Инициализирует новый экземпляр класса `completion_future`.|  
|[~ completion_future деструктор](#dtor)|Уничтожает `completion_future` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get](#get)|Ожидает завершения указанной асинхронной операции.|  
|[затем](#then)|Добавляет объект функции обратного вызова для `completion_future` объект для выполнения по завершении выполнения указанной асинхронной операции.|  
|[to_task](#to_task)|Возвращает `task` объект, соответствующий указанной асинхронной операции.|  
|[Допустимые](#valid)|Возвращает логическое значение, указывающее, связан ли объект с асинхронной операцией.|  
|[Ожидание](#wait)|Блокируется до завершения связанного асинхронной операции.|  
|[wait_for](#wait_for)|Блокируется до завершения асинхронной операции, связанные или времени, заданного параметром `_Rel_time` прошло.|  
|[wait_until](#wait_until)|Блокируется до завершения асинхронной операции, связанные или до текущего времени превышает значение, заданное параметром `_Abs_time`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор std::shared_future\<void настроек](#operator_shared_future)|Неявно преобразует `completion_future` объект `std::shared_future` объект.|  
|[operator=](#operator_eq)|Копирует содержимое указанного `completion_future` объекта в другой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `completion_future`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** concurrency  


## <a name="ctor"></a>completion_future 

Инициализирует новый экземпляр класса `completion_future`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
completion_future();  
  
completion_future(  
    const completion_future& _Other );  
  
completion_future(  
    completion_future&& _Other );  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `completion_future` Объект для копирования или перемещения.  
  
### <a name="overloads-list"></a>Список перегрузок  
  
|Имя|Описание|  
|----------|-----------------|  
|`completion_future();`|Инициализирует новый экземпляр `completion_future` класса|  
|`completion_future(const completion_future& _Other);`|Инициализирует новый экземпляр `completion_future` класса путем копирования конструктора.|  
|`completion_future(completion_future&& _Other);`|Инициализирует новый экземпляр `completion_future` класса путем перемещения конструктора.|  
  
## <a name="get"></a>Получить 

Ожидает завершения указанной асинхронной операции. Вызывает хранимую исключение, если один произошла во время асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void get() const;  
```  
  
## <a name="operator_shared_future"></a>оператор std::shared_future<void> 

Неявно преобразует `completion_future` объект `std::shared_future` объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
operator std::shared_future<void>() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `std::shared_future`.  
  
## <a name="operator_eq"></a>оператор = 

Копирует содержимое указанного `completion_future` объекта в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
completion_future&  operator= (const completion_future& _Other );    
completion_future&  operator= (completion_future&& _Other );  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 Копируемый объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `completion_future` объекта.  
  
## <a name="overloads-list"></a>Список перегрузок  
  
|Имя|Описание|  
|----------|-----------------|  
|`completion_future& operator=(const completion_future& _Other);`|Копирует содержимое указанного `completion_future` объекта в другой, используя глубокую копию.|  
|`completion_future& operator=(completion_future&& _Other);`|Копирует содержимое указанного `completion_future` объекта в другой, с помощью присваивания перемещения.|  
  
## <a name="then"></a>затем 

Добавляет объект функции обратного вызова для `completion_future` объект для выполнения по завершении выполнения указанной асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template <typename _Functor>  
void then(const _Functor & _Func ) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Functor`  
 Функтор обратного вызова.  
  
 `_Func`  
 Объект функции обратного вызова.  
  
## <a name="to_task"></a>to_task 

Возвращает `task` объект, соответствующий указанной асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
concurrency::task<void> to_task() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `task` объект, соответствующий указанной асинхронной операции.  
  
## <a name="valid"></a>Допустимые 

Получает логическое значение, которое указывает, связан ли объект с асинхронной операцией.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool valid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если объект связан с асинхронной операцией; в противном случае — `false`.  
  
## <a name="wait"></a>Ожидание 

Блокируется до завершения связанного асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void wait() const;  
```  
  
## <a name="wait_for"></a>wait_for 

Блокируется до завершения асинхронной операции, связанные или времени, который задается параметром `_Rel_time` прошло.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template <  
    class _Rep,  
    class _Period  
>  
std::future_status::future_status wait_for(  
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Rep`  
 Арифметический тип, который представляет количество тактов.  
  
 `_Period`  
 Std::ratio, представляющий количество секунд, которые должны пройти одному такту.  
  
 `_Rel_time`  
 Максимальное время ожидания завершения операции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возврат:  
  
-   `std::future_status::deferred`Если связанный асинхронная операция не выполняется.  
  
-   `std::future_status::ready`Если связанный асинхронная операция завершена.  
  
-   `std::future_status::timeout`Если указанный интервал времени.  
  
## <a name="wait_until"></a>wait_until 

Блокируется до завершения асинхронной операции, связанные или до текущего времени превышает значение, заданное параметром `_Abs_time`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
template <  
    class _Clock,  
    class _Duration  
>  
std::future_status::future_status wait_until(  
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Clock`  
 Часы, в которой эта точка время измеряется.  
  
 `_Duration`  
 Интервал времени с момента запуска `_Clock`на эпохи, после чего функция истекает время ожидания.  
  
 `_Abs_time`  
 На момент времени, после которого истекает функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возврат:  
  
1.  `std::future_status::deferred`Если связанный асинхронная операция не выполняется.  
  
2.  `std::future_status::ready`Если связанный асинхронная операция завершена.  
  
3.  `std::future_status::timeout`Если задан период времени.  
  
## <a name="dtor"></a>~ completion_future 

Уничтожает `completion_future` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
~completion_future();  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

