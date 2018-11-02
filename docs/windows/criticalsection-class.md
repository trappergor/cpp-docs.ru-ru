---
title: CriticalSection - класс
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: dd34206741ba8fee8b283e22b6e8eefb3b3efb0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651156"
---
# <a name="criticalsection-class"></a>CriticalSection - класс

Представляет объект критической секции.

## <a name="syntax"></a>Синтаксис

```cpp
class CriticalSection;
```

## <a name="members"></a>Участники

### <a name="constructor"></a>Конструктор

name                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::CriticalSection](#criticalsection)        | Инициализирует объект синхронизации, аналогичны объект mutex, но может использоваться только потоки одного процесса.
[CriticalSection:: ~ CriticalSection](#tilde-criticalsection) | Деинициализирует и уничтожает текущего `CriticalSection` объекта.

### <a name="public-methods"></a>Открытые методы

Имя                                 | Описание
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::IsValid](#isvalid) | Указывает, является ли допустимым текущую критическую секцию.
[CriticalSection::Lock](#lock)       | Ожиданий владения объектом указанного критический раздел. Функция возвращает при предоставлении владельцем вызывающего потока.
[CriticalSection::TryLock](#trylock) | Пытается войти в критическую секцию без блокировки. Если вызов был успешным, вызывающий поток получает права владения критический раздел.

### <a name="protected-data-members"></a>Защищенные члены данных

name                        | Описание
--------------------------- | ----------------------------------------
[CriticalSection::cs_](#cs) | Объявляет член данных критического раздела.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="tilde-criticalsection"></a>CriticalSection:: ~ CriticalSection

Деинициализирует и уничтожает текущего `CriticalSection` объекта.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsection"></a>CriticalSection::CriticalSection

Инициализирует объект синхронизации, аналогичны объект mutex, но может использоваться только потоки одного процесса.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Параметры

*spinCount*<br/>
Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о критических секциях и прокруток см. в разделе `InitializeCriticalSectionAndSpinCount` работать в `Synchronization` раздел документации по Windows API.

## <a name="cs"></a>CriticalSection::cs_

Объявляет член данных критического раздела.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Примечания

Эти данные-член защищены.

## <a name="isvalid"></a>CriticalSection::IsValid

Указывает, является ли допустимым текущую критическую секцию.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию всегда возвращает **true**.

## <a name="lock"></a>CriticalSection::Lock

Ожиданий владения объектом указанного критический раздел. Функция возвращает при предоставлении владельцем вызывающего потока.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Определенный пользователем объект критической секции.

### <a name="return-value"></a>Возвращаемое значение

Объект блокировки, который можно использовать, чтобы разблокировать текущую критическую секцию.

### <a name="remarks"></a>Примечания

Первая функция `Lock` влияет на текущий объект критической секции. Вторая функция `Lock` влияет на указанную пользователем критическую секцию.

## <a name="trylock"></a>CriticalSection::TryLock

Пытается войти в критическую секцию без блокировки. Если вызов был успешным, вызывающий поток получает права владения критический раздел.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Определенный пользователем объект критической секции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если критический раздел успешно передан или текущий поток уже владеет критическим разделом. Нуль, если другой поток уже владеет критическим разделом.

### <a name="remarks"></a>Примечания

Первая функция `TryLock` влияет на текущий объект критической секции. Вторая функция `TryLock` влияет на указанную пользователем критическую секцию.
