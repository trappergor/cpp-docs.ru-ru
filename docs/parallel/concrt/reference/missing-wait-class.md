---
title: Класс missing_wait
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: 7e515a33bfa827bba5329182cd3b79764495d728
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531122"
---
# <a name="missingwait-class"></a>Класс missing_wait

Этот класс описывает исключение, возникающее при наличии задач, для которых по-прежнему запланирован объект `task_group` или `structured_task_group` на момент выполнения деструктора объекта. Это исключение не создается, если деструктор достигается из-за освобождения стека в результате исключения.

## <a name="syntax"></a>Синтаксис

```
class missing_wait : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[missing_wait](#ctor)|Перегружен. Создает объект `missing_wait`.|

## <a name="remarks"></a>Примечания

Отсутствует поток исключений, вы несете ответственность за вызов либо `wait` или `run_and_wait` метод `task_group` или `structured_task_group` объект, прежде чем разрешить этот объект для уничтожения. Среда выполнения создает это исключение, как это означает, что вы забыли вызвать `wait` или `run_and_wait` метод.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`missing_wait`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> missing_wait

Создает объект `missing_wait`.

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[Класс structured_task_group](structured-task-group-class.md)
