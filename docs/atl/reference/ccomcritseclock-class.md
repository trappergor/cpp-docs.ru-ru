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
ms.openlocfilehash: e0f68f48867510c270c7c69e325a796f274198d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607003"
---
# <a name="ccomcritseclock-class"></a>Класс CComCritSecLock

Этот класс предоставляет методы для блокировки и разблокировки объект критической секции.

## <a name="syntax"></a>Синтаксис

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Параметры

*TLock*<br/>
Объект для блокировки и разблокировать.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Конструктор.|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::Lock](#lock)|Вызовите этот метод, чтобы заблокировать объект критической секции.|
|[CComCritSecLock::Unlock](#unlock)|Вызовите этот метод, чтобы разблокировать объект критической секции.|

## <a name="remarks"></a>Примечания

Этот класс используется для блокирования и разблокирования объектов более безопасным способом, чем с [класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) или [класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock

Конструктор.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Объект критической секции.

*bInitialLock*<br/>
Состояние начального блокировки: **true** означает, что заблокирована.

### <a name="remarks"></a>Примечания

Инициализирует объект критической секции.

##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock

Деструктор

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Примечания

Разблокирует объект критической секции.

##  <a name="lock"></a>  CComCritSecLock::Lock

Вызовите этот метод, чтобы заблокировать объект критической секции.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если объект успешно заблокирован или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Если объект уже заблокирован, в отладочных сборках возникнет ошибка УТВЕРЖДЕНИЯ.

##  <a name="unlock"></a>  CComCritSecLock::Unlock

Вызовите этот метод, чтобы разблокировать объект критической секции.

```
void Unlock() throw();
```

### <a name="remarks"></a>Примечания

Если объект уже разблокирован, в отладочных сборках возникнет ошибка УТВЕРЖДЕНИЯ.

## <a name="see-also"></a>См. также

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)
