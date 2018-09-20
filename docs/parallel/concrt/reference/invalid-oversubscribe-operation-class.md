---
title: Класс invalid_oversubscribe_operation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e62dc4ad1600b2e5cc7f955c4a419d27482bb557
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433222"
---
# <a name="invalidoversubscribeoperation-class"></a>Класс invalid_oversubscribe_operation

Этот класс описывает исключение, создаваемое при вызове метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, имеющим значение `false`, без предварительного вызова метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, имеющим значение `true`.

## <a name="syntax"></a>Синтаксис

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Перегружен. Создает объект `invalid_oversubscribe_operation`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> invalid_oversubscribe_operation

Создает объект `invalid_oversubscribe_operation`.

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
