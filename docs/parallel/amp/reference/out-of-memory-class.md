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
ms.openlocfilehash: 4edc1db3c1a70a41f9a0493bd3dc484e27f99b44
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126452"
---
# <a name="out_of_memory-class"></a>out_of_memory - класс

Исключение, возникающее при сбое метода из-за нехватки памяти системы или устройства.

## <a name="syntax"></a>Синтаксис

```cpp
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор out_of_memory](#ctor)|Инициализирует новый экземпляр класса `out_of_memory`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт. h

**Пространство имен** : Concurrency
## <a name="ctor"></a>out_of_memory

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

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
