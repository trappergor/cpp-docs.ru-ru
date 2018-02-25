---
title: "Класс completion_future | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24f7012f7fdd9aaeb2443665187aba4eef483e0f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="completionfuture-class"></a>Класс completion_future
Представляет будущих соответствующий асинхронную операцию C++ AMP.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class completion_future;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор completion_future](#ctor)|Инициализирует новый экземпляр класса `completion_future`.|  
|[~ completion_future деструктор](#dtor)|Уничтожает `completion_future` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[get](#get)|Ожидает завершения указанной асинхронной операции.|  
|[then](#then)|Добавляет объект обратного вызова функции `completion_future` объект для выполнения по завершении выполнения указанной асинхронной операции.|  
|[to_task](#to_task)|Возвращает `task` объект, соответствующий указанной асинхронной операции.|  
|[Допустимые](#valid)|Возвращает логическое значение, указывающее, связан ли объект с асинхронной операцией.|  
|[Ожидание](#wait)|Блокируется до завершения связанного асинхронной операции.|  
|[wait_for](#wait_for)|Блокируется до завершения асинхронной операции, связанные или времени, заданного параметром `_Rel_time` прошло.|  
|[wait_until](#wait_until)|Блокируется до завершения асинхронной операции, связанные или до текущего времени превышает значение, заданное параметром `_Abs_time`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор std::shared_future\<void >](#operator_shared_future)|Неявно преобразует `completion_future` объект `std::shared_future` объекта.|  
|[оператор=](#operator_eq)|Копирует содержимое указанного `completion_future` объекта в другой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `completion_future`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** concurrency  


## <a name="ctor"></a> completion_future 

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
  
|name|Описание:|  
|----------|-----------------|  
|`completion_future();`|Инициализирует новый экземпляр `completion_future` класса|  
|`completion_future(const completion_future& _Other);`|Инициализирует новый экземпляр `completion_future` , копируя конструктор.|  
|`completion_future(completion_future&& _Other);`|Инициализирует новый экземпляр `completion_future` класса путем перемещения конструктора.|  
  
## <a name="get"></a> Получить 

Ожидает завершения указанной асинхронной операции. Создается хранимой исключение, если один обнаружена во время асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void get() const;  
```  
  
## <a name="operator_shared_future"></a> оператор std::shared_future<void> 

Неявно преобразует `completion_future` объект `std::shared_future` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
operator std::shared_future<void>() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `std::shared_future`.  
  
## <a name="operator_eq"></a> оператор = 

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
  
|name|Описание:|  
|----------|-----------------|  
|`completion_future& operator=(const completion_future& _Other);`|Копирует содержимое указанного `completion_future` объекта в другой, с помощью глубокой копией.|  
|`completion_future& operator=(completion_future&& _Other);`|Копирует содержимое указанного `completion_future` объекта в другой, с помощью присваивания перемещения.|  
  
## <a name="then"></a> затем 

Добавляет объект обратного вызова функции `completion_future` объект для выполнения по завершении выполнения указанной асинхронной операции.  
  
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
  
## <a name="to_task"></a> to_task 

Возвращает `task` объект, соответствующий указанной асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
concurrency::task<void> to_task() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `task` объект, соответствующий указанной асинхронной операции.  
  
## <a name="valid">Допустимые</a> 

Получает логическое значение, которое указывает, связан ли объект с асинхронной операцией.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool valid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если объект связан с асинхронной операцией; в противном случае `false`.  
  
## <a name="wait">Ожидание</a> 

Блокируется до завершения связанного асинхронной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
void wait() const;  
```  
  
## <a name="wait_for"></a> wait_for 

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
 Std::ratio, представляющее число секунд, которые должны пройти одному такту.  
  
 `_Rel_time`  
 Максимальное время ожидания завершения операции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает:  
  
-   `std::future_status::deferred` Если связанный асинхронная операция не выполняется.  
  
-   `std::future_status::ready` Если указанной асинхронной операции завершения.  
  
-   `std::future_status::timeout` Если указанный интервал времени.  
  
## <a name="wait_until"></a> wait_until 

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
 Интервал времени с момента запуска `_Clock`его начала эпохи, после чего функция выдаст ошибку времени ожидания.  
  
 `_Abs_time`  
 На момент времени, после чего функция имеет время ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает:  
  
1.  `std::future_status::deferred` Если связанный асинхронная операция не выполняется.  
  
2.  `std::future_status::ready` Если указанной асинхронной операции завершения.  
  
3.  `std::future_status::timeout` Если задан период времени.  
  
## <a name="dtor"></a> ~ completion_future 

Уничтожает `completion_future` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
~completion_future();  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
