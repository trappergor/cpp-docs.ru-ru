---
title: Класс task_completion_event
ms.date: 11/04/2016
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
ms.openlocfilehash: 9d0ab271b20eb02c1dc4cb8e54cf2632eead4325
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293892"
---
# <a name="taskcompletionevent-class"></a>Класс task_completion_event

Класс `task_completion_event` позволяет отложить выполнение задачи до выполнения условия или запустить задачу в ответ на внешнее событие.

## <a name="syntax"></a>Синтаксис

```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```

#### <a name="parameters"></a>Параметры

*_ResultType*<br/>
Тип результата данного класса `task_completion_event`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[task_completion_event](#ctor)|Создает объект `task_completion_event`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[set](#set)|Перегружен. Задает событие завершения задачи.|
|[set_exception](#set_exception)|Перегружен. Распространяет исключение для всех задач, связанных с этим событием.|

## <a name="remarks"></a>Примечания

Если требуется создать задачу, которая будет завершена и, тем самым, будет иметь запланированное продолжение для выполнения в определенный момент в будущем, следует использовать задачу, созданную из события завершения задачи. Объект `task_completion_event` должен быть того же типа, что и создаваемая задача. Вызов метода set для события завершения задачи со значением такого типа приведет к завершению соответствующей задачи и предоставит это значение как результат продолжения.

Если о событии завершения задачи не сообщается, все задачи, созданные из этого события, будут отменены при его уничтожении.

`task_completion_event` ведет себя как интеллектуальный указатель и должен передаваться по значению.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task_completion_event`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Пространство имен:** concurrency

##  <a name="set"></a> Набор

Задает событие завершения задачи.

```
bool set(_ResultType _Result) const ;

bool set() const ;
```

### <a name="parameters"></a>Параметры

*_Result*<br/>
Результат, чтобы задать для события.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает **true** если ему удалось успешно задать событие. Он возвращает **false** Если событие уже задано.

### <a name="remarks"></a>Примечания

При наличии множества или параллельных вызовов к `set`, только первый вызов будет успешен и его результат (если таковые имеются) будут храниться в событие завершения задачи. Остальные наборы игнорируются и метод возвращает значение false. При установке события завершения задачи все задачи, созданные из событий будут немедленно завершены, что их продолжения, если таковые имеются, будут планироваться. Объекты завершения задачи `_ResultType` отличное от **void** передаст значение их продолжения.

##  <a name="set_exception"></a> set_exception

Распространяет исключение для всех задач, связанных с этим событием.

```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```

### <a name="parameters"></a>Параметры

*_E*<br/>
Тип исключения.

*_Except*<br/>
Исключение, чтобы задать.

*_ExceptionPtr*<br/>
Задать указатель исключение.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="ctor"></a> task_completion_event

Создает объект `task_completion_event`.

```
task_completion_event();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
