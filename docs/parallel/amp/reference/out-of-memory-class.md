---
title: out_of_memory - класс
ms.date: 11/04/2016
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
ms.openlocfilehash: e716d4952bdb9634cc0d195285d3a65c5c06b0a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336806"
---
# <a name="out_of_memory-class"></a>out_of_memory - класс

Исключение, которое выбрасывается, когда метод выходит из строя из-за отсутствия системы или памяти устройства.

## <a name="syntax"></a>Синтаксис

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[out_of_memory конструктор](#ctor)|Инициализирует новый экземпляр класса `out_of_memory`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="out_of_memory"></a><a name="ctor"></a>out_of_memory

Инициализирует новый экземпляр класса.

### <a name="syntax"></a>Синтаксис

```cpp
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Текстовое описание ошибки.

### <a name="return-value"></a>Возвращаемое значение

Новый экземпляр класса `out_of_memory`.

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
