---
title: Класс nested_scheduler_missing_detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7c862cdf778b726a4d416ea490f5da9c3d7eb01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414892"
---
# <a name="nestedschedulermissingdetach-class"></a>Класс nested_scheduler_missing_detach

Этот класс описывает исключение, которое возникает, когда исполняющая среда с параллелизмом обнаруживает, что вы не вызвали метод `CurrentScheduler::Detach` для контекста, который присоединился ко второму планировщику с помощью метода `Attach` объекта `Scheduler`.

## <a name="syntax"></a>Синтаксис

```
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Перегружен. Создает объект `nested_scheduler_missing_detach`.|

## <a name="remarks"></a>Примечания

Это исключение возникает, только когда один планировщик вложен внутрь другого путем вызова метода `Attach` объекта `Scheduler` для контекста, которым уже владеет другой планировщик или к которому он уже прикреплен. Среда выполнения с параллелизмом возможности создает это исключение, если сценарий может обнаружить в качестве вспомогательного средства поиск неполадки. Не каждый экземпляр игнорирования для вызова `CurrentScheduler::Detach` метод гарантированно вызывают это исключение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> nested_scheduler_missing_detach

Создает объект `nested_scheduler_missing_detach`.

```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс Scheduler](scheduler-class.md)
