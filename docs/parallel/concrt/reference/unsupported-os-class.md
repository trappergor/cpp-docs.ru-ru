---
title: Класс unsupported_os
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: 8277827aa8713ef57731a3e0da0898829b9fa9fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186370"
---
# <a name="unsupportedos-class"></a>Класс unsupported_os

Данный класс описывает исключение, которое создается при использовании неподдерживаемой операционной системы.

## <a name="syntax"></a>Синтаксис

```
class unsupported_os : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[unsupported_os](#ctor)|Перегружен. Создает объект `unsupported_os`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`unsupported_os`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> unsupported_os

Создает объект `unsupported_os`.

```
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
