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
ms.openlocfilehash: ff54357055d373db98f469b071edc75fce75e0b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336797"
---
# <a name="runtime_exception-class"></a>runtime_exception - класс

Базовый тип для исключений в библиотеке ускоренного массового параллелизма (AMP).

### <a name="syntax"></a>Синтаксис

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[runtime_exception конструктор](#ctor)|Инициализирует новый экземпляр класса `runtime_exception`.|
|[«runtime_exception деструктор](#dtor)|Уничтожает `runtime_exception` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get_error_code](#get_error_code)|Возвращает код ошибки, вызвавший исключение.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператора](#operator_eq)|Копирует содержимое указанного `runtime_exception` объекта в этот.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="runtime_exception-constructor"></a><a name="ctor"></a>runtime_exception конструктор

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
HRESULT ошибки, которая вызвала исключение.

*_Other*<br/>
Копируемый объект `runtime_exception`.

### <a name="return-value"></a>Возвращаемое значение

Объект `runtime_exception`.

## <a name="runtime_exception-destructor"></a><a name="dtor"></a>«runtime_exception деструктор

Уничтожает объект.

### <a name="syntax"></a>Синтаксис

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a><a name="get_error_code"></a>get_error_code

Возвращает код ошибки, вызвавший исключение.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

HRESULT ошибки, которая вызвала исключение.

## <a name="operator"></a><a name="operator_eq"></a>оператора

Копирует содержимое указанного `runtime_exception` объекта в этот.

### <a name="syntax"></a>Синтаксис

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Копируемый объект `runtime_exception`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `runtime_exception` этот объект.

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
