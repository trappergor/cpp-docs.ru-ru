---
title: HANDLENullTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: 41e06cc50f36a077a34d992c416a543e5bf9b593
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371475"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits - структура

Определяет общие характеристики непервоначальной ручки.

## <a name="syntax"></a>Синтаксис

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | ---------------------
`Type` | Синоним для HANDLE.

### <a name="public-methods"></a>Открытые методы

Имя                                                  | Описание
----------------------------------------------------- | -----------------------------
[HANDLENullTraits::Закрыть](#close)                     | Закрывает указанную ручку.
[HANDLENullTraits::GetInvalidValue](#getinvalidvalue) | Представляет недействительную ручку.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="handlenulltraitsclose"></a><a name="close"></a>HANDLENullTraits::Закрыть

Закрывает указанную ручку.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Ручка, чтобы закрыть.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если ручка *h* закрыта успешно; в противном случае, **ложные**.

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLENullTraits::GetInvalidValue

Представляет недействительную ручку.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение `nullptr`.
