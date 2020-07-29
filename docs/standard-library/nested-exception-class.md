---
title: Класс nested_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6ae95880f0bc18928ed9bd4f6b6da14722f6ec60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212193"
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

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#op_as)||

### <a name="functions"></a>Функции

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|Создает хранимое исключение.|
|[nested_ptr](#nested_ptr)|Возвращает сохраненное исключение.|

### <a name="operator"></a><a name="op_as"></a>Оператор =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Хранимое исключение, записанное этим `nested_exception` объектом.

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Remarks

Если `nested_ptr()` возвращает пустой указатель, функция вызывает `std::terminate()` . В противном случае он создает хранимое исключение, захваченное **`*this`** .

## <a name="requirements"></a>Требования

**Заголовок:**\<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[Класс Exception](../standard-library/exception-class.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
