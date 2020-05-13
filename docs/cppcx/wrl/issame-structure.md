---
title: IsSame - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
ms.openlocfilehash: fcaf33309521b44163022e0ffa9b1e03e53e2551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371348"
---
# <a name="issame-structure"></a>IsSame - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип.

*T2*<br/>
Другой тип.

## <a name="remarks"></a>Remarks

Определяет, совпадают ли указанные типы друг с другом.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

Имя                    | Описание
----------------------- | --------------------------------------------------
[IsSame::стоимость](#value) | Указывает, совпадают ли заданные типы друг с другом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsSame`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="issamevalue"></a><a name="value"></a>IsSame::стоимость

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Remarks

Указывает, совпадают ли заданные типы друг с другом.

`value`**верно,** если параметры шаблона одинаковы, и **ложны,** если параметры шаблона отличаются.
