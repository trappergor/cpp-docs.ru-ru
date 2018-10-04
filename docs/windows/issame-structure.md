---
title: Issame-структура | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26ecab69c2c31db51e137ad012bf67541e03a095
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788465"
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

**Пространство имен:** Microsoft::wrl:: Details

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

`value` — `true` Если параметров шаблона являются одинаковыми, и `false` Если параметры шаблона различаются.
