---
title: uninitialized_object - класс
ms.date: 11/04/2016
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 1c431364aee0f1d1e75059abdb023ae52cf92155
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279347"
---
# <a name="uninitializedobject-class"></a>uninitialized_object - класс

Исключение, возникающее, когда используется неинициализированный объект.

## <a name="syntax"></a>Синтаксис

```
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[uninitialized_object, конструктор](#ctor)|Инициализирует новый экземпляр класса `uninitialized_object`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** параллелизм
## <a name="uninitialized_object__ctor"></a> unsupported_feature

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

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
