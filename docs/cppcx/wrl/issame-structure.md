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
ms.openlocfilehash: b659f832756b79289181db34fa8d6fc0d974609d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161281"
---
# <a name="issame-structure"></a>IsSame - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

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

## <a name="remarks"></a>Примечания

Определяет, совпадают ли указанные типы друг с другом.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

name                    | Описание
----------------------- | --------------------------------------------------
[IsSame::value](#value) | Указывает, совпадают ли заданные типы друг с другом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsSame`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="value"></a>IsSame::value

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

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

### <a name="remarks"></a>Примечания

Указывает, совпадают ли заданные типы друг с другом.

`value` — **true** Если параметров шаблона являются одинаковыми, и **false** Если параметры шаблона различаются.
