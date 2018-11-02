---
title: Класс context_self_unblock
ms.date: 11/04/2016
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
helpviewer_keywords:
- context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
ms.openlocfilehash: 5cb7fc951a4c62f4d299ce7d394e9f8268d7ed74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622174"
---
# <a name="contextselfunblock-class"></a>Класс context_self_unblock

Этот класс описывает исключение, которое создается при вызове метода `Unblock` объекта `Context` из того же контекста. Это означает попытку данного контекста разблокировать самого себя.

## <a name="syntax"></a>Синтаксис

```
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[context_self_unblock](#ctor)|Перегружен. Создает объект `context_self_unblock`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`context_self_unblock`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> context_self_unblock

Создает объект `context_self_unblock`.

```
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
