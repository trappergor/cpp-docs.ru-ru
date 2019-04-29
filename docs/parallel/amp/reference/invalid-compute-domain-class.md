---
title: invalid_compute_domain - класс
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351723"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain - класс

Исключение, возникающее, когда среда выполнения не может запустить ядро с помощью вычислительного домена, указанного в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) место вызова.

## <a name="syntax"></a>Синтаксис

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[invalid_compute_domain конструктор](#ctor)|Инициализирует новый экземпляр класса `invalid_compute_domain`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** параллелизм

## <a name="ctor"></a> invalid_compute_domain

Инициализирует новый экземпляр класса.

## <a name="syntax"></a>Синтаксис

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описание ошибки.

### <a name="return-value"></a>Возвращаемое значение

Экземпляр `invalid_compute_domain` класса

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
