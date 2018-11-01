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
ms.openlocfilehash: d70425f414b998eb67e3937c2c126dd3eda0c00d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571370"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits - структура

Определяет общие характеристики дескриптора неинициализированным.

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
[HANDLENullTraits::Close](#close)                     | Закрывает указанный дескриптор.
[HANDLENullTraits::GetInvalidValue](#getinvalidvalue) | Представляет недопустимый дескриптор.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLENullTraits::Close

Закрывает указанный дескриптор.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Чтобы закрыть дескриптор.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если обрабатывать *h* Закрыто успешно; в противном случае — значение **false**.

## <a name="getinvalidvalue"></a>HANDLENullTraits::GetInvalidValue

Представляет недопустимый дескриптор.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение `nullptr`.
