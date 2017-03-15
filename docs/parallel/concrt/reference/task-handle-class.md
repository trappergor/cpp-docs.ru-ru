---
title: "Класс task_handle | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
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
ms.openlocfilehash: b113cf519f4326650dc1ed4d20dd2ed00921eda9
ms.lasthandoff: 02/24/2017

---
# <a name="taskhandle-class"></a>Класс task_handle
Класс `task_handle` представляет отдельный параллельный рабочий элемент. Он инкапсулирует инструкции и данные, необходимые для выполнения части работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, который будет вызываться для выполнения работы, представленной `task_handle` объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор task_handle](#ctor)|Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.|  
|[~ task_handle деструктор](#dtor)|Уничтожает `task_handle` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор Operator()](#task_handle__operator_call)|Оператор вызова функции, который среда выполнения вызывает для выполнения работ дескриптора задачи.|  
  
## <a name="remarks"></a>Примечания  
 `task_handle`объекты, которые могут использоваться в сочетании с `structured_task_group` или более общим `task_group` объекта, чтобы разделить трудозатраты на параллельные задачи. Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Обратите внимание, что автор `task_handle` объект отвечает за поддержание времени существования, созданного объекта `task_handle` объекта, пока он больше не требуется средой выполнения с параллелизмом. Как правило, это означает, что `task_handle` объект не должен уничтожения пока не `wait` или `run_and_wait` метод `task_group` или `structured_task_group` вызывался при которой она помещается в очередь.  
  
 `task_handle`объекты обычно используются в сочетании с лямбда-выражения C++. Поскольку вы не знаете истинный тип лямбда-выражения, [make_task](concurrency-namespace-functions.md#make_task) функция обычно используется для создания `task_handle` объекта.  
  
 Среда выполнения создает копию рабочей функции, передаваемой `task_handle` объекта. Таким образом, изменения состояния, возникающие в функции объекта, передается `task_handle` объект не будет отображаться в копию этого объекта функции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `task_handle`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nametaskhandleoperatorcalla-operator"></a><a name="task_handle__operator_call"></a>Operator() 

 Оператор вызова функции, который среда выполнения вызывает для выполнения работ дескриптора задачи.  
  
```  
void operator()() const;

 
```  
  
##  <a name="a-nametaskhandlectora-taskhandle"></a><a name="task_handle__ctor"></a>task_handle 

 Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Параметры  
 `_Func`  
 Функция, которая будет вызываться для выполнения работы, представленной `task_handle` объекта. Это может быть лямбда-функтор, указатель на функцию или другой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()`.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения создает копию рабочей функции, передаваемой конструктору. Таким образом, изменения состояния, возникающие в функции объекта, передается `task_handle` объект не будет отображаться в копию этого объекта функции.  
  
##  <a name="a-namedtora-taskhandle"></a><a name="dtor"></a>~ task_handle 

 Уничтожает `task_handle` объекта.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс task_group](task-group-class.md)   
 [Класс structured_task_group](structured-task-group-class.md)

