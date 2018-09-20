---
title: Класс ScheduleGroup | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90687a1e0cb77694fce9e60004f3e43d0ea9acf0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427424"
---
# <a name="schedulegroup-class"></a>Класс ScheduleGroup

Представляет абстракцию для группы расписаний. Группы расписаний организуют набор связанных работ, которые выигрывают от планирования в непосредственной близости друг от друга: во времени (путем выполнения другой задачи в той же группе перед перемещением в другую группу) или в пространстве (путем выполнения нескольких элементов в той же группе в том же узле NUMA или физическом сокете).

## <a name="syntax"></a>Синтаксис

```
class ScheduleGroup;
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[~ Деструктор ScheduleGroup](#dtor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Id](#id)|Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.|
|[Ссылки](#reference)|Увеличивает значение счетчика ссылок группы расписания.|
|[Релиз](#release)|Уменьшает значение счетчика ссылок группы планировщика.|
|[ScheduleTask](#scheduletask)|Планирует задачу нетребовательный к ресурсам в пределах группы расписания.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ScheduleGroup`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="id"></a> Идентификатор

Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.

##  <a name="operator_delete"></a> оператор delete

Объект `ScheduleGroup` объект уничтожается внутренним образом средой выполнения при выходе всех внешних ссылок на него. Его невозможно удалить явно.

```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
const char *,
    int);
```

### <a name="parameters"></a>Параметры

*_PObject*<br/>
Указатель на объект для удаления.

##  <a name="reference"></a> Справочник по

Увеличивает значение счетчика ссылок группы расписания.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик ссылок на новое значение.

### <a name="remarks"></a>Примечания

Это обычно используется для управления жизненным циклом группы расписаний для композиции. Когда счетчик ссылок группы расписания становится равным нулю, группы расписаний удаляется средой выполнения. Группы расписаний, создаваемых с помощью [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) метод, или [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) метод начинается с одним счетчиком ссылок.

##  <a name="release"></a> выпуск

Уменьшает значение счетчика ссылок группы планировщика.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Вновь уменьшается на единицу счетчик.

### <a name="remarks"></a>Примечания

Это обычно используется для управления жизненным циклом группы расписаний для композиции. Когда счетчик ссылок группы расписания становится равным нулю, группы расписаний удаляется средой выполнения. После вызова `Release` метод определенное количество раз, чтобы удалить Создание ссылки на число и любые дополнительные материалы, размещенные с помощью `Reference` метод, вы не сможете использовать группы расписания. Это приведет к неопределенному поведению.

Группы расписаний, связанный с определенным экземпляром планировщика. Необходимо убедиться, что все ссылки на группы расписаний будут освобождены до все ссылки на планировщик освобождаются, поскольку последний может привести к уничтожению планировщика. Это приведет к неопределенному поведению.

##  <a name="dtor"></a> ~ ScheduleGroup

```
virtual ~ScheduleGroup();
```

##  <a name="scheduletask"></a> ScheduleTask

Планирует задачу нетребовательный к ресурсам в пределах группы расписания.

```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```

### <a name="parameters"></a>Параметры

*_Proc*<br/>
Указатель на функцию, необходимо выполнить, чтобы выполнять тело упрощенная задача.

*_Data*<br/>
Указатель void к данным, которые будут передаваться в качестве параметра в теле задачи.

### <a name="remarks"></a>Примечания

Вызов `ScheduleTask` метод неявно помещает значение счетчика ссылок на группы расписаний, которая удаляется средой выполнения в подходящее время после выполнения задачи.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс CurrentScheduler](currentscheduler-class.md)<br/>
[Класс Scheduler](scheduler-class.md)<br/>
[Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

