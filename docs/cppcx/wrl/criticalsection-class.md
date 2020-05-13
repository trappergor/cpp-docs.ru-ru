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
ms.openlocfilehash: 5deb89e795d1886ca316886ae1ea260ce1f36fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372591"
---
# <a name="criticalsection-class"></a>CriticalSection - класс

Представляет критический объект раздела.

## <a name="syntax"></a>Синтаксис

```cpp
class CriticalSection;
```

## <a name="members"></a>Участники

### <a name="constructor"></a>Конструктор

Имя                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Критическийраздел::Критическаясекция](#criticalsection)        | Инициализирует объект синхронизации, похожий на объект mutex, но может использоваться только потоками одного процесса.
[Критическийраздел::-КритическийРаздел](#tilde-criticalsection) | Деприноизгизирует и `CriticalSection` уничтожает текущий объект.

### <a name="public-methods"></a>Открытые методы

Имя                                 | Описание
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[Критическийраздел::Действительно](#isvalid) | Указывает, является ли текущий критический раздел допустимом.
[Критическийраздел::Блокировка](#lock)       | Ожидает сябовку в праве собственности на указанный объект критического раздела. Функция возвращается, когда поток вызова получает право собственности.
[Критическийраздел::TryLock](#trylock) | Попытки войти в критический раздел без блокировки. Если вызов выполняется успешно, поток вызова берет на себя ответственность за критический раздел.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Описание
--------------------------- | ----------------------------------------
[Критическийраздел::cs_](#cs) | Объявляет сятводок критическиважного участника данных раздела.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>Критическийраздел::-КритическийРаздел

Деприноизгизирует и `CriticalSection` уничтожает текущий объект.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>Критическийраздел::Критическаясекция

Инициализирует объект синхронизации, похожий на объект mutex, но может использоваться только потоками одного процесса.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Параметры

*счет спина*<br/>
Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о критических разделах и спин-ктятах см. `InitializeCriticalSectionAndSpinCount` `Synchronization`

## <a name="criticalsectioncs_"></a><a name="cs"></a>Критическийраздел::cs_

Объявляет сятводок критическиважного участника данных раздела.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Remarks

Эти данные-член защищены.

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>Критическийраздел::Действительно

Указывает, является ли текущий критический раздел допустимом.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию, всегда **возвращается верно**.

## <a name="criticalsectionlock"></a><a name="lock"></a>Критическийраздел::Блокировка

Ожидает сябовку в праве собственности на указанный объект критического раздела. Функция возвращается, когда поток вызова получает право собственности.

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

### <a name="remarks"></a>Remarks

Первая функция `Lock` влияет на текущий объект критической секции. Вторая функция `Lock` влияет на указанную пользователем критическую секцию.

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>Критическийраздел::TryLock

Попытки войти в критический раздел без блокировки. Если вызов выполняется успешно, поток вызова берет на себя ответственность за критический раздел.

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

Ненулевое значение, если критический раздел успешно введен или текущий поток уже владеет критическим разделом. Ноль, если другой поток уже владеет критическим разделом.

### <a name="remarks"></a>Remarks

Первая функция `TryLock` влияет на текущий объект критической секции. Вторая функция `TryLock` влияет на указанную пользователем критическую секцию.
