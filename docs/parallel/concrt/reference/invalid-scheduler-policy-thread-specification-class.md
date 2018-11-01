---
title: Класс invalid_scheduler_policy_thread_specification
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: b74439d1fca9ea990258ca5f7e36c865a2c49455
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491342"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>Класс invalid_scheduler_policy_thread_specification

Данный класс описывает исключение, создаваемое при попытке установить ограничения параллельности объекта `SchedulerPolicy` таким образом, чтобы значение ключа `MinConcurrency` было меньше, чем значение ключа `MaxConcurrency`.

## <a name="syntax"></a>Синтаксис

```
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification] (недопустимый scheduler политики — значение class.md #ctor|Перегружен. Создает объект `invalid_scheduler_policy_value`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification

Создает объект `invalid_scheduler_policy_value`.

```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс SchedulerPolicy](schedulerpolicy-class.md)
