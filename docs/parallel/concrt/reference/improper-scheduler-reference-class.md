---
title: Класс improper_scheduler_reference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5a061ca3c7bb39d90608685e04b62da9b2e83fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410420"
---
# <a name="improperschedulerreference-class"></a>Класс improper_scheduler_reference

Данный класс описывает исключение, которое создается при вызове метода `Reference` на объекте `Scheduler`, который завершает работу, из контекста, который не является частью этого планировщика.

## <a name="syntax"></a>Синтаксис

```
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|Перегружен. Создает объект `improper_scheduler_reference`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> improper_scheduler_reference

Создает объект `improper_scheduler_reference`.

```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс Scheduler](scheduler-class.md)
