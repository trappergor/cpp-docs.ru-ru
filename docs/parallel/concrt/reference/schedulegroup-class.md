---
title: "Класс ScheduleGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::ScheduleGroup
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
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
ms.openlocfilehash: 424b2f53f39bce57c85e44f0df54928acdac399a
ms.lasthandoff: 02/24/2017

---
# <a name="schedulegroup-class"></a>Класс ScheduleGroup
Представляет абстракцию для группы расписаний. Группы расписаний организуют набор связанных работ, которые выигрывают от планирования в непосредственной близости друг от друга: во времени (путем выполнения другой задачи в той же группе перед перемещением в другую группу) или в пространстве (путем выполнения нескольких элементов в той же группе в том же узле NUMA или физическом сокете).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ Деструктор ScheduleGroup](#dtor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ID-метод](#id)|Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.|  
|[Reference-метод](#reference)|Увеличивает значение счетчика ссылок группы расписания.|  
|[Release-метод](#release)|Уменьшает значение счетчика ссылок группы планировщика.|  
|[ScheduleTask-метод](#scheduletask)|Назначает легкое задание в группы расписаний.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ScheduleGroup`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameida-id"></a><a name="id"></a>Идентификатор 

 Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>оператор delete 

 Объект `ScheduleGroup` объект уничтожается внутренне средой выполнения при выпуске всех внешних ссылок на него. Его невозможно удалить явно.  
  
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
 `_PObject`  
 Указатель на объект для удаления.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>Ссылка 

 Увеличивает значение счетчика ссылок группы расписания.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Увеличенное счетчик.  
  
### <a name="remarks"></a>Примечания  
 Обычно используется для управления временем существования группы планирования для композиции. Когда счетчик ссылок группы расписаний становится равным нулю, группа расписаний удаляется средой выполнения. Группа планирования, создаваемых с помощью [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) метода или [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) метода начинается с одним счетчиком ссылок.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Выпуск 

 Уменьшает значение счетчика ссылок группы планировщика.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вновь уменьшается на единицу счетчик.  
  
### <a name="remarks"></a>Примечания  
 Обычно используется для управления временем существования группы планирования для композиции. Когда счетчик ссылок группы расписаний становится равным нулю, группа расписаний удаляется средой выполнения. После вызова `Release` метод определенное количество раз для удаления Создание ссылки на число и любые дополнительные ссылки, размещенные с помощью `Reference` метода, нельзя использовать группы расписания. Это приведет к неопределенному поведению.  
  
 Группа планирования связан с определенным экземпляром планировщика. Необходимо убедиться, что все ссылки на группу расписаний освобождаются до освобождения всех ссылок на планировщик, поскольку последние может привести к уничтожению планировщика. Это приведет к неопределенному поведению.  
  
##  <a name="a-namedtora-schedulegroup"></a><a name="dtor"></a>~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 Назначает легкое задание в группы расписаний.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Proc`  
 Указатель на функцию, выполняемую для выполнения тексте упрощенная задача.  
  
 `_Data`  
 Указатель void на данные, на которые будут передаваться в качестве параметра в теле задачи.  
  
### <a name="remarks"></a>Примечания  
 Вызов `ScheduleTask` метод неявно помещает значение счетчика ссылок на группу расписаний, которая удаляется средой выполнения в соответствующее время после выполнения задачи.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс CurrentScheduler](currentscheduler-class.md)   
 [Класс планировщика](scheduler-class.md)   
 [Планировщик заданий](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




