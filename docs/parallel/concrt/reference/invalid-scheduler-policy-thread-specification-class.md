---
title: Класс invalid_scheduler_policy_thread_specification | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc0f52bc36157bcbc1e6adaa28f786a01ac05263
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404921"
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
