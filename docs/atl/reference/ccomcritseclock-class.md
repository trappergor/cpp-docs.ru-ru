---
title: Класс CComCritSecLock
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: 4b2ef093c1142b592ad2a6605a08bd8c34a643ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748071"
---
# <a name="ccomcritseclock-class"></a>Класс CComCritSecLock

Этот класс предоставляет методы блокировки и разблокировки объекта критических секций.

## <a name="syntax"></a>Синтаксис

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Параметры

*TLock*<br/>
Объект, который будет заблокирован и разблокирован.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Конструктор.|
|[CComCritSecLock::: »CComCritSecLock](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::Блокировка](#lock)|Вызовите этот метод, чтобы заблокировать объект критического сечения.|
|[CComCritSecLock::Разблокировка](#unlock)|Вызовите этот метод, чтобы разблокировать критический объект раздела.|

## <a name="remarks"></a>Remarks

Используйте этот класс для блокировки и разблокировки объектов более безопасным способом, чем с [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md) или [CComAutoCriticalSection Class.](../../atl/reference/ccomautocriticalsection-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>CComCritSecLock::CComCritSecLock

Конструктор.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Объект критического сечения.

*bInitialLock*<br/>
Начальное состояние блокировки: **истинные** средства заблокированы.

### <a name="remarks"></a>Remarks

Инициализирует объект критического сечения.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>CComCritSecLock::: »CComCritSecLock

Деструктор

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Remarks

Разблокирует объект критического сечения.

## <a name="ccomcritseclocklock"></a><a name="lock"></a>CComCritSecLock::Блокировка

Вызовите этот метод, чтобы заблокировать объект критического сечения.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если объект был успешно заблокирован, или ошибка HRESULT при сбое.

### <a name="remarks"></a>Remarks

Если объект уже заблокирован, в сборках отладок возникает ошибка ASSERT.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>CComCritSecLock::Разблокировка

Вызовите этот метод, чтобы разблокировать критический объект раздела.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Remarks

Если объект уже разблокирован, в сборках отладок возникает ошибка ASSERT.

## <a name="see-also"></a>См. также раздел

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)
