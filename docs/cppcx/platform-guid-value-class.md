---
title: Класс значения Platform::Guid
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: f63b2bb4fd5f809861622a4f6b255ee3725564b6
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816594"
---
# <a name="platformguid-value-class"></a>Класс значения Platform::Guid

Представляет тип [GUID](/previous-versions/cc317743(v%3dmsdn.10)) в системе типов среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
public value struct Guid
```

### <a name="members"></a>Участники

`Platform::Guid` содержит методы `Equals()`, `GetHashCode()` и `ToString()`, производные от [класса Platform:: Object](../cppcx/platform-object-class.md), и метод `GetTypeCode()`, производный от [класса Platform:: Type](../cppcx/platform-type-class.md). `Platform::Guid` также содержит следующие члены.

|Член|Описание|
|------------|-----------------|
|[Guid](#ctor)|Инициализирует новый экземпляр класса `Platform::Guid`.|
|[operator==](#operator-equality)|Оператор равенства.|
|[operator!=](#operator-inequality)|Оператор неравенства.|
|[operator&lt;](#operator-less)|Оператор "меньше".|
|[operator()](#operator-call)|Преобразует `Platform::Guid` в `GUID`.|

### <a name="remarks"></a>Примечания

Чтобы создать новый `Platform::Guid`, используйте статический метод [Windows:: Foundation:: GuidHelper:: креатеневгуид](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) .

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Платформа

**Метаданные:** platform.winmd

## <a name="ctor"></a>Конструкторы GUID:: GUID

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

*б*<br/>
Следующий байт `GUID`.

*k*<br/>
Следующий байт `GUID`.

*m*<br/>
Значение `GUID` в виде [структуры GUID](/previous-versions/cc317743(v%3dmsdn.10)).

*n*<br/>
Оставшиеся 8 байт `GUID`.

## <a name="operator-equality"></a>Оператор GUID:: operator = =

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

Значение true, если два экземпляра `Platform::Guid` равны.

### <a name="remarks"></a>Примечания

Предпочитать использование оператора `==` вместо статического метода [Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) .

## <a name="operator-inequality"></a>Оператор GUID:: operator! =

Сравнивает два экземпляра `Platform::Guid` на неравенство.

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

Значение true, если два экземпляра `Platform::Guid` не равны.

## <a name="operator-less"></a>Оператор GUID:: operator @ no__t-1

Сравнивает два экземпляра `Platform::Guid` для упорядочения.

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

Значение true, если *GUID1* упорядочивается до *GUID2*. Упорядочение лексикографическим порядком после обработки каждого `Platform::Guid`, как если бы это массив 4 32-разрядных значений без знака. Это не порядок, используемый SQL Server или .NET Framework, а также не совпадает с лексикографическом упорядочиванием по строковому представлению.

Этот оператор предоставляется таким образом, чтобы объекты `Guid` могли быть более легко использованы C++ стандартной библиотекой.

## <a name="operator-call"></a>Оператор GUID:: operator ()

Неявно преобразует `Platform::Guid` в [структуру GUID](/previous-versions/cc317743(v%3dmsdn.10)).

### <a name="syntax"></a>Синтаксис

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Возвращаемое значение

[Структура Guid](/previous-versions/cc317743(v%3dmsdn.10)).

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
