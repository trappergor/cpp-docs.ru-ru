---
title: Класс CCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 2c89647afc8a9a8c6564d25afe20d48818a643f2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291045"
---
# <a name="ccriticalsection-class"></a>Класс CCriticalSection

Класс представляет «критическую секцию» — объект синхронизации, позволяющий одному потоку за раз, чтобы получить доступ к ресурсу или раздел кода.

## <a name="syntax"></a>Синтаксис

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Создает объект `CCriticalSection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CCriticalSection::Lock](#lock)|Использовать для получения доступа к `CCriticalSection` объекта.|
|[CCriticalSection::Unlock](#unlock)|Освобождает объект `CCriticalSection`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Извлекает указатель на внутренний объект CRITICAL_SECTION.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|Объект CRITICAL_SECTION.|

## <a name="remarks"></a>Примечания

Критические разделы полезны в тех случаях, когда изменение данных или другой управляемый ресурс можно предоставить только один поток за раз. Например добавление узлов в связанный список — это процесс, который должен осуществляться только одним потоком за раз. С помощью `CCriticalSection` объект для управления в связанном списке, только один поток за раз можно получить доступ к списку.

> [!NOTE]
>  Функциональные возможности `CCriticalSection` предоставляет класс фактический объект Win32 CRITICAL_SECTION.

Критические секции используются вместо мьютексы (см. в разделе [CMutex](../../mfc/reference/cmutex-class.md)) когда важно повысить скорость и ресурс не будет использоваться через границы процессов.

Существует два способа использования `CCriticalSection` объект: изолированное и внедренное в классе.

- Автономный метод, используемый изолированного `CCriticalSection` объекта, создания `CCriticalSection` объекта при необходимости. После успешного возвращения из конструктора, явно заблокировать объект с помощью вызова [блокировки](#lock). Вызовите [Unlock](#unlock) после доступа к критической секции. Этот метод при яснее кому-либо чтение исходный код, вероятность возникновения ошибки необходимо помнить о том, блокировать и разблокировать критический раздел до и после доступа.

   Более предпочтительным методом является использование [CSingleLock](../../mfc/reference/csinglelock-class.md) класса. Есть также `Lock` и `Unlock` метод, но вам не нужно беспокоиться о разблокировании ресурсов при возникновении исключения.

- Внедренный метод, вы можете поделиться класс с несколькими потоками, добавив `CCriticalSection`-член данных типа для класса и блокировка элемента данных, при необходимости.

Дополнительные сведения об использовании `CCriticalSection` объектов, см. в статье [Многопоточность: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection

Создает объект `CCriticalSection`.

```
CCriticalSection();
```

### <a name="remarks"></a>Примечания

Для доступа к или выпуска `CCriticalSection` следует создать [CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функций-членов. Если `CCriticalSection` объекта используется автономный, вызвать его [Unlock](#unlock) функция-член для его освобождения.

Если конструктору не удается выделить память необходимые системные, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически вызывается исключение.

### <a name="example"></a>Пример

  См. в примере [CCriticalSection::Lock](#lock).

##  <a name="lock"></a>  CCriticalSection::Lock

Вызовите эту функцию-член для получения доступа к объект критической секции.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
`Lock` игнорирует значение этого параметра.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lock` блокирующий вызов, который не возвращает значение до объект критической секции переводится в сигнальное состояние (становится доступной).

При необходимости ограниченную по времени ожидания, можно использовать [CMutex](../../mfc/reference/cmutex-class.md) вместо объекта `CCriticalSection` объекта.

Если `Lock` не удается выделить память необходимые системные, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически вызывается исключение.

### <a name="example"></a>Пример

В этом примере показано вложенных критического раздела, контролируя доступ к общему ресурсу (статический `_strShared` объекта) с помощью общего `CCriticalSection` объекта. `SomeMethod` Функции показано обновление общего ресурса безопасным образом.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

##  <a name="m_sect"></a>  CCriticalSection::m_sect

Содержит объект критической секции, который используется всеми `CCriticalSection` методы.

```
CRITICAL_SECTION m_sect;
```

##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *

Извлекает объект CRITICAL_SECTION.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы получить указатель на внутренний объект CRITICAL_SECTION.

##  <a name="unlock"></a>  CCriticalSection::Unlock

Выпуски `CCriticalSection` объекта для использования другим потоком.

```
BOOL Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CCriticalSection` поток был владельцем объекта, и выпуска выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если `CCriticalSection` , используется изолированное, `Unlock` должен вызываться сразу после завершения работы использование ресурса, контролируются в критический раздел. Если [CSingleLock](../../mfc/reference/csinglelock-class.md) используется объект, `CCriticalSection::Unlock` будет вызван объектом блокировки `Unlock` функция-член.

### <a name="example"></a>Пример

  См. в примере [CCriticalSection::Lock](#lock).

## <a name="see-also"></a>См. также

[Класс CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMutex](../../mfc/reference/cmutex-class.md)
