---
title: Класс invalid_oversubscribe_operation
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 7a879fc2da2f963cd4b5ea5fcd7e9506f86ce051
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140836"
---
# <a name="invalid_oversubscribe_operation-class"></a>Класс invalid_oversubscribe_operation

Этот класс описывает исключение, возникающее при вызове метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, для которого задано **значение false** без предварительного вызова метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, для которого установлено значение **true**.

## <a name="syntax"></a>Синтаксис

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Перегружен. Создает объект `invalid_oversubscribe_operation`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h

**Пространство имен:** concurrency

## <a name="ctor"></a>invalid_oversubscribe_operation

Создает объект `invalid_oversubscribe_operation`.

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
