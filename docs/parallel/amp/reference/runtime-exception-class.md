---
title: runtime_exception - класс
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: 024ede0f05dfd646bcebe7acd2cfb86b5c54f6d1
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565497"
---
# <a name="runtimeexception-class"></a>runtime_exception - класс

Базовый тип для исключений в библиотеке C++ Accelerated Massive Parallelism (AMP).

### <a name="syntax"></a>Синтаксис

```
class runtime_exception : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Конструктор runtime_exception](#ctor)|Инициализирует новый экземпляр класса `runtime_exception`.|
|[~ runtime_exception деструктор](#dtor)|Уничтожает `runtime_exception` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[get_error_code](#get_error_code)|Возвращает код ошибки, вызвавшей исключение.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `runtime_exception` в данный объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** параллелизм

## <a name="ctor"></a>  Конструктор runtime_exception

Инициализирует новый экземпляр класса.

### <a name="syntax"></a>Синтаксис

```
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описание ошибки, вызвавшей исключение.

*_Hresult*<br/>
Значение HRESULT ошибки, вызвавшей исключение.

*_Другое*<br/>
`runtime_exception` Копируемый объект.

### <a name="return-value"></a>Возвращаемое значение

Объект `runtime_exception`.

## <a name="dtor"></a>  ~ runtime_exception деструктор

Уничтожает объект.

### <a name="syntax"></a>Синтаксис

```
virtual ~runtime_exception() throw();
```

## <a name="geterrorcode"></a>get_error_code

Возвращает код ошибки, вызвавшей исключение.

### <a name="syntax"></a>Синтаксис

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT ошибки, вызвавшей исключение.

## <a name="operator_eq"></a>  оператор=
  Копирует содержимое указанного объекта `runtime_exception` в данный объект.

### <a name="syntax"></a>Синтаксис

```
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`runtime_exception` Копируемый объект.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `runtime_exception` объекта.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
