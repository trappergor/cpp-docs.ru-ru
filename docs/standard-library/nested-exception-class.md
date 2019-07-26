---
title: Класс nested_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 5741b3aa255f915500f5fe79ab5374c8c86f8814
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460181"
---
# <a name="nestedexception-class"></a>Класс nested_exception

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

Хранимое исключение, записанное `nested_exception` этим объектом.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Примечания

Если `nested_ptr()` возвращает пустой указатель, функция вызывает `std::terminate()`. В противном случае он создает хранимое исключение `*this`, захваченное.

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс Exception](../standard-library/exception-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
