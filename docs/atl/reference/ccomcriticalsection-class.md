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
ms.openlocfilehash: f3a4b50f8dd9bc460a209c47497e720529c40e58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246648"
---
# <a name="ccomcriticalsection-class"></a>Класс CComCriticalSection

Этот класс предоставляет методы для получения и освобождения владения объект критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|Создает и инициализирует объект критической секции.|
|[CComCriticalSection::Lock](#lock)|Получает права владельца объекта критической секции.|
|[CComCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объектом критический раздел.|
|[CComCriticalSection::Unlock](#unlock)|Освобождает владение объект критической секции.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|Объект CRITICAL_SECTION.|

## <a name="remarks"></a>Примечания

`CComCriticalSection` Аналогично класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), за исключением того, что необходимо явно инициализировать и освободит критический раздел.

Как правило, используется `CComCriticalSection` через **typedef** имя [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Это имя ссылается на `CComCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) используется.

См. в разделе [класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md) для более безопасным способом использовать этот класс, чем вызов `Lock` и `Unlock` напрямую.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection

Конструктор.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Наборы [m_sec](#m_sec) элемент данных в значение NULL.

##  <a name="init"></a>  CComCriticalSection::Init

Вызывает функцию Win32 [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), который инициализирует объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успешного выполнения E_OUTOFMEMORY или E_FAIL в случае сбоя.

##  <a name="lock"></a>  CComCriticalSection::Lock

Вызывает функцию Win32 [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection), которого ожидает, пока поток может стать владельцем объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успешного выполнения E_OUTOFMEMORY или E_FAIL в случае сбоя.

### <a name="remarks"></a>Примечания

Сначала необходимо инициализировать объект критической секции с вызовом [Init](#init) метод. Если защищенный код завершения выполнения, поток должен вызвать [Unlock](#unlock) для освобождения владения критический раздел.

##  <a name="m_sec"></a>  CComCriticalSection::m_sec

Содержит объект критической секции, который используется всеми `CComCriticalSection` методы.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>  CComCriticalSection::Term

Вызывает функцию Win32 [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), который освобождает все ресурсы, используемые объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Один раз `Term` был вызван, критически важные раздел больше не может использоваться для синхронизации.

##  <a name="unlock"></a>  CComCriticalSection::Unlock

Вызывает функцию Win32 [LeaveCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection), который освобождает владение объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Сначала получить права владельца, поток должен вызвать [блокировки](#lock) метод. Каждый вызов `Lock` требует соответствующего вызова `Unlock` для освобождения владения критический раздел.

## <a name="see-also"></a>См. также

[Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)
