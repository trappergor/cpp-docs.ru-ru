---
title: Класс CRTThreadTraits
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: e5e13bad907e76968c4d4343e6617903e309e40f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282608"
---
# <a name="crtthreadtraits-class"></a>Класс CRTThreadTraits

Этот класс предоставляет функции создания потока CRT. Этот класс используется в том случае, если поток будет использовать функции CRT.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CRTThreadTraits
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CRTThreadTraits::CreateThread](#createthread)|(Статический) Вызывайте эту функцию для создания потока, который можно использовать функции CRT.|

## <a name="remarks"></a>Примечания

Поток признаки являются классы, предоставляющие функции создания для определенного типа потока. Функция создания совпадает с той же сигнатуре и семантику Windows [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) функции.

Поток признаки используются следующие классы:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Если поток не будет использовать функции CRT, используйте [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) вместо этого.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="createthread"></a>  CRTThreadTraits::CreateThread

Вызывайте эту функцию для создания потока, который можно использовать функции CRT.

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

*lpsa*<br/>
Атрибуты безопасности для нового потока.

*dwStackSize*<br/>
Размер стека для нового потока.

*pfnThreadProc*<br/>
Процедура потока нового потока.

*pvParam*<br/>
Параметр, передаваемый в процедуру потока.

*dwCreationFlags*<br/>
Создание флагов ("0" или "CREATE_SUSPENDED").

*pdwThreadId*<br/>
[out] Адрес переменной DWORD, который, в случае успешного выполнения получает идентификатор только что созданному потоку.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор в только что созданному потоку или значение NULL в случае сбоя. Вызовите [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) Чтобы получить расширенные сведения об ошибке.

### <a name="remarks"></a>Примечания

См. в разделе [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) для получения дополнительных сведений о параметрах для этой функции.

Эта функция вызывает [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) при создании потока.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
