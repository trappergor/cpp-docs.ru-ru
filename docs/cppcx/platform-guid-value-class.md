---
title: Класс значения Platform::GUID | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e115cf74eaac194c9e5b7154898cc23e10b220eb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100435"
---
# <a name="platformguid-value-class"></a>Класс значения Platform::Guid

Представляет [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) тип в системе типов среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
public value struct Guid
```

### <a name="members"></a>Участники

Структура Guid имеет методы Equals(), GetHashCode() и ToString(), производные от [Platform::Object Class](../cppcx/platform-object-class.md), и метод GetTypeCode(), производный от [Platform::Type Class](../cppcx/platform-type-class.md). У структуры Guid также имеются следующие члены.

|Член|Описание|
|------------|-----------------|
|[Guid](#ctor)|Инициализирует новый экземпляр структуры Guid.|
|[operator==](#operator-equality)|Оператор равенства.|
|[operator!=](#operator-not-equal)|Оператор неравенства.|
|[operator()](#operator-call)|Преобразует Guid в GUID.|

### <a name="remarks"></a>Примечания

Пример создания новой структуры Platform::Guid с помощью функции Windows [CoCreateGuid](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateguid), см. в разделе [компонент WinRT: как создать GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="ctor"></a> Конструкторы GUID::GUID

Инициализирует новый экземпляр структуры Guid.

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
Первые 4 байта GUID.

*b*<br/>
Следующие 2 байта GUID.

*c*<br/>
Следующие 2 байта GUID.

*d*<br/>
Следующий байт GUID.

*e*<br/>
Следующий байт GUID.

*f*<br/>
Следующий байт GUID.

*g*<br/>
Следующий байт GUID.

*h*<br/>
Следующий байт GUID.

*i*<br/>
Следующий байт GUID.

*j*<br/>
Следующий байт GUID.

*k*<br/>
Следующий байт GUID.

*m*<br/>
GUID согласно определению.

*n*<br/>
Оставшиеся 8 байтов GUID.

## <a name="operator-equality"></a> GUID::operator ==-оператор

Сравнивает два GUID.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::Guid::operator==
```

### <a name="return-value"></a>Возвращаемое значение

Значение true, если GUID равны.

## <a name="operator-inequality"></a> GUID::operator! =-оператор

Сравнивает два GUID.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::Guid::operator!=
```

### <a name="return-value"></a>Возвращаемое значение

Значение true, если GUID не равны.

## <a name="operator-call"></a> Оператор GUID:: operator()

Неявно преобразует [структуры GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)в Platform::guid.

### <a name="syntax"></a>Синтаксис

```cpp
Platform::Guid operator();
```

### <a name="return-value"></a>Возвращаемое значение

Структура Guid.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)