---
title: HANDLETraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: 604098cd3289722767117910d6e44e272dcb8b77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371449"
---
# <a name="handletraits-structure"></a>HANDLETraits - структура

Определяет общие характеристики дескриптора.

## <a name="syntax"></a>Синтаксис

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | ---------------------
`Type` | Синоним для HANDLE.

### <a name="public-methods"></a>Открытые методы

Имя                                              | Описание
------------------------------------------------- | -----------------------------
[HANDLETraits::Закрыть](#close)                     | Закрывает указанную ручку.
[HANDLETraits::GetInvalidValue](#getinvalidvalue) | Представляет недействительную ручку.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLETraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="handletraitsclose"></a><a name="close"></a>HANDLETraits::Закрыть

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

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLETraits::GetInvalidValue

Представляет недействительную ручку.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение INVALID_HANDLE_VALUE (INVALID_HANDLE_VALUE определяется Windows).
