---
title: "Класс task_handle | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 0fef1ef7b1c02287a0113eb80be413e4a17dc1a4
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
|[task_handle](#ctor)|Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.|  
|[~ task_handle деструктор](#dtor)|Уничтожает `task_handle` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Operator()](#task_handle__operator_call)|Оператор вызова функции, который среда выполнения вызывает для выполнения работ дескриптора задачи.|  
  
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
  
##  <a name="task_handle__operator_call"></a>Operator() 

 Оператор вызова функции, который среда выполнения вызывает для выполнения работ дескриптора задачи.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a>task_handle 

 Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Параметры  
 `_Func`  
 Функция, которая будет вызываться для выполнения работы, представленной `task_handle` объекта. Это может быть лямбда-функтор, указатель на функцию или другой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()`.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения создает копию рабочей функции, передаваемой конструктору. Таким образом, изменения состояния, возникающие в функции объекта, передается `task_handle` объект не будет отображаться в копию этого объекта функции.  
  
##  <a name="dtor"></a>~ task_handle 

 Уничтожает `task_handle` объекта.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс task_group](task-group-class.md)   
 [Класс structured_task_group](structured-task-group-class.md)

