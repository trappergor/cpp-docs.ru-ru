---
title: Класс nested_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: a568a8d9a3817883656406d63c3dd948539bb385
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268526"
---
# <a name="nestedexception-class"></a>Класс nested_exception

Этот класс описывает исключение, для использования с множественным наследованием. Она фиксирует сейчас обрабатываемое исключение и сохраняет его для последующего использования.

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
|[оператор=](#op_as)||

### <a name="functions"></a>Функции

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|Создает хранимую исключение.|
|[nested_ptr](#nested_ptr)|Возвращает хранимые исключение.|

### <a name="op_as"></a> оператор =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Это исключение хранимые этим объектом `nested_exception` объекта.

### <a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Примечания

Если `nested_ptr()` возвращается указатель null, эта функция вызывает `std::terminate()`. В противном случае выдается хранимых захвачено исключение `*this`.

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс exception](../standard-library/exception-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
