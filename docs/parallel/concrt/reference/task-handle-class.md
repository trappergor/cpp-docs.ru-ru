---
title: Класс task_handle
ms.date: 11/04/2016
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: c1a12555b0b7277fd6b52d935518e4bb1f297285
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521363"
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

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения работы, представленной `task_handle` объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[task_handle](#ctor)|Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанное в качестве параметра в конструктор.|
|[~ task_handle деструктор](#dtor)|Уничтожает `task_handle` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator()](#task_handle__operator_call)|Оператор вызова функции, который среда выполнения вызывает для выполнения работы дескриптор задач.|

## <a name="remarks"></a>Примечания

`task_handle` объекты, которые могут использоваться в сочетании с `structured_task_group` или более общего `task_group` объекта, чтобы разделить трудозатраты на параллельные задачи. Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Обратите внимание, что создатель `task_handle` объект отвечает за поддержание времени существования созданного `task_handle` объекта, пока он больше не требуется средой выполнения с параллелизмом. Как правило, это означает, что `task_handle` объект не должен уничтожения либо до `wait` или `run_and_wait` метод `task_group` или `structured_task_group` вызывался при котором помещен в очередь.

`task_handle` объекты обычно используются в сочетании с лямбда-выражения в C++. Так как вы не знаете истинный тип лямбда-выражения, [make_task](concurrency-namespace-functions.md#make_task) функция обычно используется для создания `task_handle` объекта.

Среда выполнения создает копию рабочей функции, который передается `task_handle` объекта. Таким образом, изменения состояния, которые происходят в функции объекта, что передаваемый `task_handle` объект не будет отображаться в свою копию этого объекта функции.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task_handle`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="task_handle__operator_call"></a> Operator()

Оператор вызова функции, который среда выполнения вызывает для выполнения работы дескриптор задач.

```
void operator()() const;

```

##  <a name="task_handle__ctor"></a> task_handle

Создает новый `task_handle` объекта. Работа задачи выполняется путем вызова функции, указанное в качестве параметра в конструктор.

```
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Func*<br/>
Функция, которая будет вызываться для выполнения работы, представленной `task_handle` объекта. Это может быть лямбда-функтор, указатель на функцию, или любым объектом, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()`.

### <a name="remarks"></a>Примечания

Среда выполнения создает копию рабочую функцию, передайте в конструктор. Таким образом, изменения состояния, которые происходят в функции объекта, что передаваемый `task_handle` объект не будет отображаться в свою копию этого объекта функции.

##  <a name="dtor"></a> ~ task_handle

Уничтожает `task_handle` объекта.

```
~task_handle();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[Класс structured_task_group](structured-task-group-class.md)
