---
title: Класс invalid_scheduler_policy_value | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0bc8f0d34a49cf8392fec13f956f4577a67248e3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402750"
---
# <a name="invalidschedulerpolicyvalue-class"></a>Класс invalid_scheduler_policy_value

Этот класс описывает исключение, создаваемое, когда ключу политики объекта `SchedulerPolicy` присваивается недопустимое для этого ключа значение.

## <a name="syntax"></a>Синтаксис

```
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[invalid_scheduler_policy_value](invalid-scheduler-policy-thread-specification-class.md#ctor|Перегружен. Создает объект `invalid_scheduler_policy_value`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> invalid_scheduler_policy_value

Создает объект `invalid_scheduler_policy_value`.

```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс SchedulerPolicy](schedulerpolicy-class.md)
