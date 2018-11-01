---
title: Класс CSyncObject
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: d72d167be874d0776ce8da02784c2e0c267c9175
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547437"
---
# <a name="csyncobject-class"></a>Класс CSyncObject

Чисто виртуальный класс, обеспечивающий общую функциональность объектов синхронизации Win32.

## <a name="syntax"></a>Синтаксис

```
class CSyncObject : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Создает объект `CSyncObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::Lock](#lock)|Прирост доступ к объекту синхронизации.|
|[CSyncObject::Unlock](#unlock)|Прирост доступ к объекту синхронизации.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::operator ДЕСКРИПТОР](#operator_handle)|Предоставляет доступ к объекту синхронизации.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|Дескриптор к базовому объекту синхронизации.|

## <a name="remarks"></a>Примечания

Библиотеки Microsoft Foundation Class предоставляет несколько классов, производных от `CSyncObject`. Это [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CSemaphore](../../mfc/reference/csemaphore-class.md).

Сведения о том, как использовать объекты синхронизации, см. в статье [Многопоточность: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

##  <a name="csyncobject"></a>  CSyncObject::CSyncObject

Создает объект синхронизации, с указанным именем.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Параметры

*pstrName*<br/>
Имя объекта. Если значение равно NULL, *pstrName* будет иметь значение null.

##  <a name="lock"></a>  CSyncObject::Lock

Вызывайте эту функцию для получения доступа к ресурсу, управляемой объектом синхронизации.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
Указывает количество времени в миллисекундах для ожидания объекта синхронизации доступен (сигнал). Если БЕСКОНЕЧНЫЙ, `Lock` будет ждать объект переводится в сигнальное состояние перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Если объект синхронизации, получает сигнал, `Lock` вернет успешно, и поток теперь является владельцем объекта. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметра. Если объект синхронизации не был отправлен сигнал в определенное время, `Lock` возвращает сбой.

##  <a name="m_hobject"></a>  CSyncObject::m_hObject

Дескриптор к базовому объекту синхронизации.

```
HANDLE m_hObject;
```

##  <a name="operator_handle"></a>  CSyncObject::operator ДЕСКРИПТОР

Этот оператор используется, чтобы получить дескриптор `CSyncObject` объекта.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения дескриптор объекта синхронизации; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.

##  <a name="unlock"></a>  CSyncObject::Unlock

Объявление `Unlock` без параметров является чистой виртуальной функции и должны быть переопределены для всех классов, производных от `CSyncObject`.

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Не используется в реализации по умолчанию.

*lpPrevCount*<br/>
Не используется в реализации по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию объявления с двумя параметрами всегда возвращает значение TRUE. Эта функция вызывается для предоставления доступа к объект синхронизации, принадлежащий вызывающий поток. Второе объявление предоставляется для синхронизации объектов, таких как семафоры, которые позволяют более одного доступ к контролируемому ресурсу.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

