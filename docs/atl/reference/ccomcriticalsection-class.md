---
title: Класс Ккомкритикалсектион
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
ms.openlocfilehash: ee4ce32ed4ae04bc3b390af5cf104b8a0af599f8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497283"
---
# <a name="ccomcriticalsection-class"></a>Класс Ккомкритикалсектион

Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомкритикалсектион:: Ккомкритикалсектион](#ccomcriticalsection)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомкритикалсектион:: init](#init)|Создает и инициализирует объект критической секции.|
|[Ккомкритикалсектион:: Lock](#lock)|Получает владение объектом критической секции.|
|[Ккомкритикалсектион:: Term](#term)|Освобождает системные ресурсы, используемые объектом критического раздела.|
|[Ккомкритикалсектион:: Unlock](#unlock)|Освобождает владение объектом критического раздела.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Ккомкритикалсектион:: m_sec](#m_sec)|Объект CRITICAL_SECTION.|

## <a name="remarks"></a>Примечания

`CComCriticalSection`аналогичен классу [ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md), за исключением того, что необходимо явно инициализировать и освободить критический раздел.

Обычно используется `CComCriticalSection` имя **typedef** [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Это имя указывает `CComCriticalSection` , когда используется [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md) .

См. раздел [класс ккомкритсеклокк](../../atl/reference/ccomcritseclock-class.md) для более безопасного использования этого класса, нежели `Lock` вызов `Unlock` и непосредственно.

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре. h

##  <a name="ccomcriticalsection"></a>Ккомкритикалсектион:: Ккомкритикалсектион

Конструктор.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Задает для элемента данных [m_sec](#m_sec) значение null.

##  <a name="init"></a>Ккомкритикалсектион:: init

Вызывает функцию Win32 [инитиализекритикалсектион](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), которая инициализирует критически важный объект Section, содержащийся в элементе данных [m_sec](#m_sec) .

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении, E_OUTOFMEMORY или E_FAIL в случае сбоя.

##  <a name="lock"></a>Ккомкритикалсектион:: Lock

Вызывает функцию Win32 [EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection), которая ожидает, пока поток не сможет стать владельцем объекта критического раздела, содержащегося в элементе данных [m_sec](#m_sec) .

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении, E_OUTOFMEMORY или E_FAIL в случае сбоя.

### <a name="remarks"></a>Примечания

Объект критической секции сначала необходимо инициализировать с помощью вызова метода [init](#init) . После завершения выполнения защищенного кода поток должен вызвать [Unlock](#unlock) , чтобы освободить владение критической секцией.

##  <a name="m_sec"></a>Ккомкритикалсектион:: m_sec

Содержит объект критической секции, используемый всеми `CComCriticalSection` методами.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>Ккомкритикалсектион:: Term

Вызывает функцию Win32 [делетекритикалсектион](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection), которая освобождает все ресурсы, используемые объектом критического раздела, содержащимся в элементе данных [m_sec](#m_sec) .

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

После `Term` вызова критическая секция больше не может использоваться для синхронизации.

##  <a name="unlock"></a>Ккомкритикалсектион:: Unlock

Вызывает функцию Win32 [LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection), которая освобождает владение объектом критической секции, содержащимся в члене данных [m_sec](#m_sec) .

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы сначала получить владение, поток должен вызвать метод [Lock](#lock) . Каждый вызов метода `Lock` требует соответствующего `Unlock` вызова, чтобы освободить владение критическим разделом.

## <a name="see-also"></a>См. также

[Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)
