---
title: Класс operation_timed_out
ms.date: 11/04/2016
f1_keywords:
- operation_timed_out
- CONCRT/concurrency::operation_timed_out
- CONCRT/concurrency::operation_timed_out::operation_timed_out
helpviewer_keywords:
- operation_timed_out class
ms.assetid: 963efe1d-a6e0-477c-9a70-d93d8412c897
ms.openlocfilehash: 8b25a35ac359fe052f9ae3c1cb15363acfbe93e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561178"
---
# <a name="operationtimedout-class"></a>Класс operation_timed_out

Этот класс описывает исключение, создаваемое по истечении времени ожидания операции.

## <a name="syntax"></a>Синтаксис

```
class operation_timed_out : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[operation_timed_out](#ctor)|Перегружен. Создает объект `operation_timed_out`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`operation_timed_out`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> operation_timed_out

Создает объект `operation_timed_out`.

```
explicit _CRTIMP operation_timed_out(_In_z_ const char* _Message) throw();

operation_timed_out() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
