---
title: Класс CComApartment
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 92db42a45a0863f8b43f7c46da9624e424d1e488
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290109"
---
# <a name="ccomapartment-class"></a>Класс CComApartment

Этот класс предоставляет поддержку для управления помещения в модуле EXE потоков в составе пула.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CComApartment
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|Отмечает начальный адрес потока.|
|[CComApartment::GetLockCount](#getlockcount)|Возвращает текущий счетчик блокировок.|
|[CComApartment::Lock](#lock)|Увеличивает счетчик блокировки потока.|
|[CComApartment::Unlock](#unlock)|Уменьшает счетчик блокировки потока.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Содержит идентификатор потока.|
|[CComApartment::m_hThread](#m_hthread)|Содержит дескриптор потока.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Содержит текущий счетчик блокировок.|

## <a name="remarks"></a>Примечания

`CComApartment` используется [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) для управления подразделение в модуле EXE потоков в составе пула. `CComApartment` Предоставляет методы для увеличение и уменьшение блокировки подсчета в потоке.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="apartment"></a>  CComApartment::Apartment

Отмечает начальный адрес потока.

```
DWORD Apartment();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда равно 0.

### <a name="remarks"></a>Примечания

Автоматически устанавливается во время [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).

##  <a name="ccomapartment"></a>  CComApartment::CComApartment

Конструктор.

```
CComApartment();
```

### <a name="remarks"></a>Примечания

Инициализирует `CComApartment` данные-члены [m_nLockCnt](#m_nlockcnt) и [m_hThread](#m_hthread).

##  <a name="getlockcount"></a>  CComApartment::GetLockCount

Возвращает текущий счетчик блокировок.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число блокировок в потоке.

##  <a name="lock"></a>  CComApartment::Lock

Увеличивает счетчик блокировки потока.

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Вызывается средой [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Число блокировок в потоке используется для статистических целей.

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

Содержит идентификатор потока.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>  CComApartment::m_hThread

Содержит дескриптор потока.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt

Содержит текущий счетчик блокировок.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>  CComApartment::Unlock

Уменьшает счетчик блокировки потока.

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Вызывается средой [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Число блокировок в потоке используется для статистических целей.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
