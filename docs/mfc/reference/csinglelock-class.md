---
title: Класс CSingleLock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 988ade49bb7acbb3bcb759f1bdf3e565e033308f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394144"
---
# <a name="csinglelock-class"></a>Класс CSingleLock

Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.

## <a name="syntax"></a>Синтаксис

```
class CSingleLock
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Создает объект `CSingleLock`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSingleLock::IsLocked](#islocked)|Определяет, если объект заблокирован.|
|[CSingleLock::Lock](#lock)|Ожидает объекта синхронизации.|
|[CSingleLock::Unlock](#unlock)|Освобождает объект синхронизации.|

## <a name="remarks"></a>Примечания

`CSingleLock` не имеет базового класса.

Чтобы использование классов синхронизации [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CEvent](../../mfc/reference/cevent-class.md), либо необходимо создать `CSingleLock` или [CMultiLock](../../mfc/reference/cmultilock-class.md) объект для ожидания и освободить объект синхронизации. Используйте `CSingleLock` при только необходимо подождать на один объект за раз. Использовать `CMultiLock` при наличии нескольких объектов, которые можно использовать в определенное время.

Чтобы использовать `CSingleLock` объекта, вызовите его конструктор внутри функции-члена в классе управляемых ресурсов. Затем вызовите [блокирована](#islocked) функцию-член для определения доступности ресурса. Если Да, продолжите остальная часть функции-члена. Если ресурс недоступен, ожидать в течение определенного времени для освобождения ресурса либо сбой запроса. После завершения использования ресурса, либо вызвать [Unlock](#unlock) работать, если `CSingleLock` объекта будет использоваться повторно, или разрешение `CSingleLock` уничтожаемого объекта.

`CSingleLock` объекты требуют наличия объект, производный от [CSyncObject](../../mfc/reference/csyncobject-class.md). Обычно это элемент данных класса управляемых ресурсов. Дополнительные сведения об использовании `CSingleLock` объектов, см. в статье [Многопоточность: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CSingleLock`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

##  <a name="csinglelock"></a>  CSingleLock::CSingleLock

Создает объект `CSingleLock`.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Параметры

*pObject*<br/>
Указывает объект синхронизации, чтобы получить доступ. Не может принимать значение NULL.

*bInitialLock*<br/>
Указывает, следует ли изначально попытка получить доступ к предоставленным объектом.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается из функции доступа-члена управляемого ресурса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

##  <a name="islocked"></a>  CSingleLock::IsLocked

Определяет, если объект, связанный с `CSingleLock` объекта является несигнальным (недоступна).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект заблокирован; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

##  <a name="lock"></a>  CSingleLock::Lock

Вызывайте эту функцию для получения доступа к ресурсу, управляемой объектом синхронизации, передаваемое `CSingleLock` конструктор.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Параметры

*dwTimeOut*<br/>
Указывает время ожидания объекта синхронизации доступен (сигнал). Если БЕСКОНЕЧНЫЙ, `Lock` будет ждать объект переводится в сигнальное состояние перед возвратом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Если объект синхронизации, получает сигнал, `Lock` вернет успешно, и поток теперь является владельцем объекта. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметра. Если объект синхронизации не был отправлен сигнал в определенное время, `Lock` возвращает сбой.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

##  <a name="unlock"></a>  CSingleLock::Unlock

Освобождает объект синхронизации, принадлежащий `CSingleLock`.

```
BOOL Unlock();


BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Количество обращений к выпуска. Должно быть больше 0. Если указанного, приводит к превышению допустимого объекта счетчиком, счетчик не изменяется, и функция возвращает значение FALSE.

*lPrevCount*<br/>
Указывает переменную для получения предыдущее количество в объекте синхронизации. Если значение равно NULL, возвращаются счетчика.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция вызывается `CSingleLock`в деструктор.

Если нужно освободить несколько доступа счетчик семафора, используйте второй формы `Unlock` и укажите количество доступов для освобождения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMultiLock](../../mfc/reference/cmultilock-class.md)
