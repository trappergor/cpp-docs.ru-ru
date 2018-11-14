---
title: Класс Platform::ArrayReference
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: 4c297f033b78e1b7f9283f5becb9db974bb2b9ff
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522861"
---
# <a name="platformarrayreference-class"></a>Класс Platform::ArrayReference

`ArrayReference` — тип оптимизации, который можно заменить на [Platform::Array^](../cppcx/platform-array-class.md) во входных параметрах, если требуется заполнить входными данными массив в стиле языка C.

## <a name="syntax"></a>Синтаксис

```cpp
class ArrayReference
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|Инициализирует новый экземпляр класса `ArrayReference`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор ArrayReference::operator()](#operator-call)|Преобразует этот объект `ArrayReference` в `Platform::Array<T>^*`.|
|[Оператор ArrayReference::operator=](#operator-assign)|Назначает содержимое другой ссылки `ArrayReference` этому экземпляру.|

## <a name="exceptions"></a>Исключения

### <a name="remarks"></a>Примечания

Использование `ArrayReference` для заполнения массива в стиле языка C позволяет избежать дополнительной операции копирования, которая потребовалось бы при копировании сначала в переменную `Platform::Array` , а затем в массив в стиле языка C. При использовании `ArrayReference`выполняется только одна операция копирования. Пример кода см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Заголовок:** vccorlib.h

## <a name="ctor"></a>  Конструктор ArrayReference::ArrayReference

Инициализирует новый экземпляр класса [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) класса.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Параметры

*dataArg*<br/>
Указатель на данные массива.

*sizeArg*<br/>
Количество элементов в исходном массиве.

*otherArg*<br/>
Объект `ArrayReference`, данные которого будут перемещены для инициализации нового экземпляра.

### <a name="remarks"></a>Примечания

## <a name="operator-assign"></a>  ArrayReference::operator =-оператор

Присваивает указанный объект текущему [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) объекта с помощью семантики перемещения.

### <a name="syntax"></a>Синтаксис

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Параметры

*otherArg*<br/>
Присваивает перемещенный объект текущему объекту `ArrayReference`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект типа `ArrayReference`.

### <a name="remarks"></a>Примечания

`Platform::ArrayReference` — это стандартный шаблон класса C++, а не ссылочный класс.

## <a name="operator-call"></a>  Оператор arrayreference:: operator()

Преобразует текущий [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) объекта обратно в [Platform::Array](../cppcx/platform-array-class.md) класса.

### <a name="syntax"></a>Синтаксис

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для объекта типа `Array<TArg>^`

### <a name="remarks"></a>Примечания

[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) и [Platform::Array](../cppcx/platform-array-class.md) являются стандартными шаблонами класса C++, не ссылочными классами.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)