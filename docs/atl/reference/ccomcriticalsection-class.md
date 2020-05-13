---
title: Класс CComCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: f3991d217fbc201bd428ed2522a5c4c25e074928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327968"
---
# <a name="ccomcriticalsection-class"></a>Класс CComCriticalSection

Этот класс предоставляет методы получения и освобождения права собственности на объект критического раздела.

## <a name="syntax"></a>Синтаксис

```
class CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComcriticalSection::CcomcriticalSection](#ccomcriticalsection)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|Создает и инициализирует критический объект раздела.|
|[CComCriticalSection::Lock](#lock)|Получает право собственности на объект критического сечения.|
|[CComCriticalSection::Срок](#term)|Выпускает системные ресурсы, используемые критическим объектом секции.|
|[CComCriticalSection::Разблокировка](#unlock)|Выпускает право собственности на объект критического раздела.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|Объект CRITICAL_SECTION.|

## <a name="remarks"></a>Remarks

`CComCriticalSection`похож на класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), за исключением того, что вы должны явно инициализовать и выпустить критический раздел.

Как правило, `CComCriticalSection` вы используете через **имя typedef** [CriticalSection.](ccommultithreadmodel-class.md#criticalsection) Это имя `CComCriticalSection` ссылается при использовании [CComMultiThreadModel.](../../atl/reference/ccommultithreadmodel-class.md)

См [CComCritSecLock класс](../../atl/reference/ccomcritseclock-class.md) для более безопасного `Lock` `Unlock` способа использования этого класса, чем вызов и непосредственно.

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>CComcriticalSection::CcomcriticalSection

Конструктор.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Remarks

Устанавливает m_sec [данных](#m_sec) в NULL.

## <a name="ccomcriticalsectioninit"></a><a name="init"></a>CComCriticalSection::Init

Вызывает функцию Win32 [ИнициализацияCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), которая инициализирует критический объект раздела, содержащийся в [m_sec](#m_sec) члене данных.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, E_OUTOFMEMORY или E_FAIL на неудачу.

## <a name="ccomcriticalsectionlock"></a><a name="lock"></a>CComCriticalSection::Lock

Вызывает функцию Win32 [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection), которая ждет, пока поток может взять на себя ответственность за критический объект раздела, содержащийся в [m_sec](#m_sec) членов данных.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, E_OUTOFMEMORY или E_FAIL на неудачу.

### <a name="remarks"></a>Remarks

Объект критического раздела должен быть сначала инициализирован с помощью вызова к методу [Init.](#init) Когда защищенный код закончил выполнение, поток должен вызвать [Unlock,](#unlock) чтобы освободить право собственности на критический раздел.

## <a name="ccomcriticalsectionm_sec"></a><a name="m_sec"></a>CComCriticalSection::m_sec

Содержит критический объект раздела, `CComCriticalSection` который используется всеми методами.

```
CRITICAL_SECTION m_sec;
```

## <a name="ccomcriticalsectionterm"></a><a name="term"></a>CComCriticalSection::Срок

Вызывает функцию Win32 [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection), которая выпускает все ресурсы, используемые критическим объектом раздела, содержащимся в [m_sec](#m_sec) члене данных.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Remarks

После `Term` вызова критический раздел больше не может использоваться для синхронизации.

## <a name="ccomcriticalsectionunlock"></a><a name="unlock"></a>CComCriticalSection::Разблокировка

Вызывает функцию Win32 [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection), которая выпускает право собственности на критический объект раздела, содержащийся в [m_sec](#m_sec) члене данных.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Remarks

Для первого получения права собственности поток должен вызвать метод [блокировки.](#lock) Каждый `Lock` вызов требует соответствующего `Unlock` вызова для освобождения собственности на критический раздел.

## <a name="see-also"></a>См. также раздел

[CComFakeCriticalSection класс](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)
