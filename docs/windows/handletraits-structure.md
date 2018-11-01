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
ms.openlocfilehash: 4dd2cde62d36c46926e703e6fb649e2ae4ef7811
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590077"
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
[HANDLETraits::Close](#close)                     | Закрывает указанный дескриптор.
[HANDLETraits::GetInvalidValue](#getinvalidvalue) | Представляет недопустимый дескриптор.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLETraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLETraits::Close

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

## <a name="getinvalidvalue"></a>HANDLETraits::GetInvalidValue

Представляет недопустимый дескриптор.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение INVALID_HANDLE_VALUE (INVALID_HANDLE_VALUE определяется Windows).
