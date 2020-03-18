---
title: Класс nested_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: ed58eb6cc074b54ae6801d2b11089af9a79f8c8f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441617"
---
# <a name="nested_exception-class"></a>Класс nested_exception

Класс описывает исключение для использования с множественным наследованием. Он фиксирует обрабатываемое в настоящее время исключение и сохраняет его для последующего использования.

## <a name="syntax"></a>Синтаксис

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>Члены

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор=](#op_as)||

### <a name="functions"></a>Функции

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|Создает хранимое исключение.|
|[nested_ptr](#nested_ptr)|Возвращает сохраненное исключение.|

### <a name="op_as"></a>Оператор =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Хранимое исключение, захваченное данным объектом `nested_exception`.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Remarks

Если `nested_ptr()` возвращает пустой указатель, функция вызывает `std::terminate()`. В противном случае он создает хранимое исключение, захваченное `*this`.

## <a name="requirements"></a>Требования

**Заголовок:** \<> исключения

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[класс исключения](../standard-library/exception-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
