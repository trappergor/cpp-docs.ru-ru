---
title: Класс значения Platform::Guid
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: ad71ed4965a3dd4846c9ba5d8ed2627ed8f7e056
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334655"
---
# <a name="platformguid-value-class"></a>Класс значения Platform::Guid

Представляет тип [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) в системе типов среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
public value struct Guid
```

### <a name="members"></a>Участники

`Platform::Guid` имеет `Equals()`, `GetHashCode()`, и `ToString()` методы, производных от [Platform::Object Class](../cppcx/platform-object-class.md)и `GetTypeCode()` метод, производный от [класс Platform::Type](../cppcx/platform-type-class.md). `Platform::Guid` также имеет следующие члены.

|Член|Описание|
|------------|-----------------|
|[Guid](#ctor)|Инициализирует новый экземпляр класса `Platform::Guid`.|
|[operator==](#operator-equality)|Оператор равенства.|
|[operator!=](#operator-inequality)|Оператор неравенства.|
|[оператор&lt;](#operator-less)|Меньше, чем оператор.|
|[operator()](#operator-call)|Преобразует `Platform::Guid` в `GUID`.|

### <a name="remarks"></a>Примечания

Пример того, как создать новый `Platform::Guid` с помощью функции Windows [CoCreateGuid](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateguid), см. в разделе [компонент WinRT: Как создать GUID?](https://www.eternalcoding.com/?p=383)

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="ctor"></a> Конструкторы GUID::GUID

Инициализирует новый экземпляр класса `Platform::Guid`.

### <a name="syntax"></a>Синтаксис

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>Параметры

*a*<br/>
Первые 4 байта `GUID`.

*b*<br/>
Следующие 2 байта `GUID`.

*c*<br/>
Следующие 2 байта `GUID`.

*d*<br/>
Следующий байт `GUID`.

*e*<br/>
Следующий байт `GUID`.

*f*<br/>
Следующий байт `GUID`.

*g*<br/>
Следующий байт `GUID`.

*h*<br/>
Следующий байт `GUID`.

*i*<br/>
Следующий байт `GUID`.

*j*<br/>
Следующий байт `GUID`.

*k*<br/>
Следующий байт `GUID`.

*m*<br/>
Объект `GUID` в форме [структуры GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931).

*n*<br/>
Оставшиеся 8 байтов `GUID`.

## <a name="operator-equality"></a> GUID::operator ==-оператор

Сравнивает два экземпляра `Platform::Guid` на предмет их равенства.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*GUID1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*GUID2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение true, если два `Platform::Guid` они равны.

## <a name="operator-inequality"></a> GUID::operator! =-оператор

Сравнивает два `Platform::Guid` экземпляров на предмет их неравенства.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*GUID1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*GUID2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение true, если два `Platform::Guid` они не равны.

## <a name="operator-less"></a> GUID::operator&lt; оператор

Сравнивает два `Platform::Guid` экземпляров для сортировки.

### <a name="syntax"></a>Синтаксис

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Параметры

*GUID1*<br/>
Первый экземпляр `Platform::Guid` для сравнения.

*GUID2*<br/>
Второй экземпляр `Platform::Guid` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение true, если *guid1* упорядочен до *guid2*. Упорядочение лексикографическим после обращаясь с каждым `Platform::Guid` , если это массив из четырех 32-разрядных беззнаковых значений. Это не упорядочения, используемыми с SQL Server или .NET Framework и не так же, как лексикографическое упорядочение по строковое представление.

Этот оператор предоставляется таким образом, чтобы `Guid` объекты можно было более легко стандартной библиотекой C++.

## <a name="operator-call"></a> Оператор GUID:: operator()

Неявно преобразует `Platform::Guid` для [структуры GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931).

### <a name="syntax"></a>Синтаксис

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [структуры GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931).

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
