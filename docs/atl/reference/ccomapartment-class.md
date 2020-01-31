---
title: Класс Ккомапартмент
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
ms.openlocfilehash: 5f4c7fc356e61210e9b99bf9989b1bb3f0abc98a
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821679"
---
# <a name="ccomapartment-class"></a>Класс Ккомапартмент

Этот класс обеспечивает поддержку управления апартаментом в модуле EXE в пуле потоков.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CComApartment
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Name|Описание|
|----------|-----------------|
|[Ккомапартмент:: Ккомапартмент](#ccomapartment)|Конструктор.|

### <a name="public-methods"></a>Общедоступные методы

|Name|Описание|
|----------|-----------------|
|[Ккомапартмент:: апартамент](#apartment)|Помечает начальный адрес потока.|
|[Ккомапартмент:: Жетлокккаунт](#getlockcount)|Возвращает текущее число блокировок потока.|
|[Ккомапартмент:: Lock](#lock)|Увеличивает число блокировок потока.|
|[Ккомапартмент:: Unlock](#unlock)|Уменьшает счетчик блокировок потока.|

### <a name="public-data-members"></a>Открытые элементы данных

|Name|Описание|
|----------|-----------------|
|[Ккомапартмент:: m_dwThreadID](#m_dwthreadid)|Содержит идентификатор потока.|
|[Ккомапартмент:: m_hThread](#m_hthread)|Содержит маркер потока.|
|[Ккомапартмент:: m_nLockCnt](#m_nlockcnt)|Содержит текущее число блокировок потока.|

## <a name="remarks"></a>Заметки

`CComApartment` используется [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md) для управления апартаментом в модуле exe в пуле потоков. `CComApartment` предоставляет методы для увеличения и уменьшения числа блокировок в потоке.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="apartment"></a>Ккомапартмент:: апартамент

Помечает начальный адрес потока.

```
DWORD Apartment();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда равно 0.

### <a name="remarks"></a>Заметки

Автоматически задается во время [ккомаутосреадмодуле:: init](../../atl/reference/ccomautothreadmodule-class.md#init).

##  <a name="ccomapartment"></a>Ккомапартмент:: Ккомапартмент

Конструктор.

```
CComApartment();
```

### <a name="remarks"></a>Заметки

Инициализирует `CComApartment`ные члены данных [m_nLockCnt](#m_nlockcnt) и [m_hThread](#m_hthread).

##  <a name="getlockcount"></a>Ккомапартмент:: Жетлокккаунт

Возвращает текущее число блокировок потока.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число блокировок в потоке.

##  <a name="lock"></a>Ккомапартмент:: Lock

Увеличивает число блокировок потока.

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Заметки

Вызывается функцией [ккомаутосреадмодуле:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Счетчик блокировок в потоке используется для статистических целей.

##  <a name="m_dwthreadid"></a>Ккомапартмент:: m_dwThreadID

Содержит идентификатор потока.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>Ккомапартмент:: m_hThread

Содержит маркер потока.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>Ккомапартмент:: m_nLockCnt

Содержит текущее число блокировок потока.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>Ккомапартмент:: Unlock

Уменьшает счетчик блокировок потока.

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Заметки

Вызывается методом [ккомаутосреадмодуле:: Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Счетчик блокировок в потоке используется для статистических целей.

## <a name="see-also"></a>См. также:

[Обзор класса](../../atl/atl-class-overview.md)
