---
title: Класс unsupported_feature
ms.date: 11/04/2016
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 155e96762d47b340ac078fad791f3078dba9a871
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497152"
---
# <a name="unsupportedfeature-class"></a>Класс unsupported_feature

Исключение, возникающее, когда используется неподдерживаемое свойство.

## <a name="syntax"></a>Синтаксис

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[unsupported_feature конструктор](#ctor)|Создает новый экземпляр класса `unsupported_feature` исключение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature__ctor"></a> unsupported_feature

  Создает новый экземпляр исключения unsupported_feature.

### <a name="syntax"></a>Синтаксис

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описание ошибки.

### <a name="return-value"></a>Возвращаемое значение

Объект `unsupported_feature`.

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
