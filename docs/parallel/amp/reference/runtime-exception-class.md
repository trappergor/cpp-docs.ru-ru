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
ms.openlocfilehash: 6ad784720833d2ae5de7d653d132ba144aec2677
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126386"
---
# <a name="runtime_exception-class"></a>runtime_exception - класс

Базовый тип для исключений в библиотеке C++ ускоренного параллелизма (amp).

### <a name="syntax"></a>Синтаксис

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор runtime_exception](#ctor)|Инициализирует новый экземпляр класса `runtime_exception`.|
|[Деструктор ~ runtime_exception](#dtor)|Уничтожает объект `runtime_exception`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[get_error_code](#get_error_code)|Возвращает код ошибки, вызвавший исключение.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `runtime_exception` в этот объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт. h

**Пространство имен** : Concurrency

## <a name="ctor"></a>Конструктор runtime_exception

Инициализирует новый экземпляр класса.

### <a name="syntax"></a>Синтаксис

```cpp
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
Значение HRESULT ошибки, вызвавшее исключение.

*_Other*<br/>
Копируемый объект `runtime_exception`.

### <a name="return-value"></a>Возвращаемое значение

Объект `runtime_exception`.

## <a name="dtor"></a>Деструктор ~ runtime_exception

Уничтожает объект.

### <a name="syntax"></a>Синтаксис

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a>get_error_code

Возвращает код ошибки, вызвавший исключение.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение HRESULT ошибки, вызвавшее исключение.

## <a name="operator_eq"></a>  оператор=
  Копирует содержимое указанного объекта `runtime_exception` в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Копируемый объект `runtime_exception`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `runtime_exception`.

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
