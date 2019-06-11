---
title: Класс unsupported_feature
ms.date: 03/27/2019
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 451318bfbcfb9c5e002677556944e3499c0ed5fb
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525414"
---
# <a name="unsupportedfeature-class"></a>Класс unsupported_feature

Исключение, возникающее, когда используется неподдерживаемое свойство.

## <a name="syntax"></a>Синтаксис

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[unsupported_feature конструктор](#unsupported_feature)|Создает новый экземпляр класса `unsupported_feature` исключение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature"></a> unsupported_feature

  Создает новый экземпляр класса `unsupported_feature` исключение.

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

**Пространство имен:** параллелизм

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
