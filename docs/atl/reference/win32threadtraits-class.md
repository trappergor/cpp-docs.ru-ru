---
title: Класс Win32ThreadTraits
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: d086a42f5dcdf005d10c8853776da66b691a8e11
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495479"
---
# <a name="win32threadtraits-class"></a>Класс Win32ThreadTraits

Этот класс предоставляет функцию создания для потока Windows. Используйте этот класс, если поток не будет использовать функции CRT.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class Win32ThreadTraits
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Win32ThreadTraits:: CreateThread](#createthread)|Статически Вызовите эту функцию, чтобы создать поток, который не должен использовать функции CRT.|

## <a name="remarks"></a>Примечания

Признаки потоков — это классы, которые предоставляют функцию создания для определенного типа потока. Функция создания имеет ту же сигнатуру и семантику, что и функция Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) .

Признаки потоков используются в следующих классах:

- [ксреадпул](../../atl/reference/cthreadpool-class.md)

- [кворкерсреад](../../atl/reference/cworkerthread-class.md)

Если поток будет использовать функции CRT, вместо него следует использовать [кртсреадтраитс](../../atl/reference/crtthreadtraits-class.md) .

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="createthread"></a>Win32ThreadTraits:: CreateThread

Вызовите эту функцию, чтобы создать поток, который не должен использовать функции CRT.

```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```

### <a name="parameters"></a>Параметры

*лпса*<br/>
Атрибуты безопасности для нового потока.

*двстакксизе*<br/>
Размер стека для нового потока.

*пфнсреадпрок*<br/>
Потоковая процедура нового потока.

*пвпарам*<br/>
Параметр, передаваемый в процедуру потока.

*двкреатионфлагс*<br/>
Флаги создания (0 или CREATE_SUSPENDED).

*пдвсреадид*<br/>
заполняет Адрес переменной типа DWORD, которая в случае успешного выполнения получает идентификатор созданного потока.

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер вновь созданного потока или значение NULL при сбое. Вызовите [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы получить расширенные сведения об ошибке.

### <a name="remarks"></a>Примечания

Дополнительные сведения о параметрах этой функции см. в разделе [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) .

Эта функция вызывает `CreateThread` метод, чтобы создать поток.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
