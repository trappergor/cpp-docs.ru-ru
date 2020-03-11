---
title: Определения типов ATL
ms.date: 11/04/2016
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
ms.openlocfilehash: f3db32e85ea9cba1e946db6259c00c621650e969
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857110"
---
# <a name="atl-typedefs"></a>Определения типов ATL

Библиотека активных шаблонов включает следующие определения типов.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|Определяется как typedef на основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|
|[_ATL_COM_MODULE](#_atl_com_module)|Определяется как typedef на основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|
|[_ATL_MODULE](#_atl_module)|Определяется как typedef на основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|
|[_ATL_WIN_MODULE](#_atl_win_module)|Определяется как typedef на основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|
|[ATL_URL_PORT](#atl_url_port)|Тип, используемый для указания номера порта в [фигурных скобках](../../atl/reference/curl-class.md) .|
|[ккомдиспатчдривер](#ccomdispatchdriver)|Этот класс управляет указателями на интерфейс COM.|
|[ккомглобалссреадмодел](#ccomglobalsthreadmodel)|Вызывает соответствующие методы модели потоков независимо от используемой потоковой модели.|
|[ккомобжектсреадмодел](#ccomobjectthreadmodel)|Вызывает соответствующие методы модели потоков независимо от используемой потоковой модели.|
|[кконтаинедвиндов](#ccontainedwindow)|Этот класс является специализацией `CContainedWindowT`.|
|[кпас](#cpath)|Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CString`.|
|[кпаса](#cpatha)|Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CStringA`.|
|[кпасв](#cpathw)|Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CStringW`.|
|[ксимплеваларрай](#csimplevalarray)|Представляет массив для хранения простых типов.|
|[дефаултсреадтраитс](#defaultthreadtraits)|Класс признаков потока по умолчанию.|
|[лпкурл](#lpcurl)|Указатель [на постоянный объект](../../atl/reference/curl-class.md) , являющийся константой.|
|[лпурл](#lpurl)|Указатель на [фигурный](../../atl/reference/curl-class.md) объект.|

##  <a name="_atl_base_module"></a>_ATL_BASE_MODULE

Определяется как typedef на основе _ATL_BASE_MODULE70.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Remarks

Используется в каждом проекте ATL. На основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

Классы, являющиеся частью классов модулей ATL 7,0, являются производными от структуры _ATL_BASE_MODULE.  Дополнительные сведения о классах модулей ATL см. в разделе [Классы модулей com](../../atl/com-modules-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре. h

##  <a name="_atl_com_module"></a>_ATL_COM_MODULE

Определяется как typedef на основе _ATL_COM_MODULE70.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Remarks

Используется проектами ATL, использующими функции COM. На основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="_atl_module"></a>_ATL_MODULE

Определяется как typedef на основе _ATL_MODULE70.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>Требования

**Заголовок.**

### <a name="remarks"></a>Remarks

На основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

##  <a name="_atl_win_module"></a>_ATL_WIN_MODULE

Определяется как typedef на основе _ATL_WIN_MODULE70.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Remarks

Используется любыми проектами ATL, использующими функции для работы с окнами. На основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="atl_url_port"></a>ATL_URL_PORT

Тип, используемый для указания номера порта в [фигурных скобках](curl-class.md) .

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil. h

##  <a name="ccomdispatchdriver"></a>ккомдиспатчдривер

Этот класс управляет указателями на интерфейс COM.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="ccomglobalsthreadmodel"></a>ккомглобалссреадмодел

Вызывает соответствующие методы модели потоков независимо от используемой потоковой модели.

```
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>Remarks

В зависимости от модели потоков, используемой приложением, имя **typedef** `CComGlobalsThreadModel` ссылается либо на [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) , либо на [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имена для ссылки на класс критической секции.

> [!NOTE]
> `CComGlobalsThreadModel` не ссылается на класс [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md).

Использование `CComGlobalsThreadModel` освобождает вас от указания конкретного класса потоковой модели. Независимо от используемой потоковой модели, будут вызываться соответствующие методы.

Помимо `CComGlobalsThreadModel`, ATL предоставляет имя **typedef** [ккомобжектсреадмодел](#ccomobjectthreadmodel). Класс, на который ссылается каждая `typedef`, зависит от используемой потоковой модели, как показано в следующей таблице.

|typedef|Единая Организация|Потоковое подразделение|Свободная организация потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Используйте `CComObjectThreadModel` в одном классе объекта. Используйте `CComGlobalsThreadModel` в глобально доступном для вашей программе объекте или при необходимости защитить ресурсы модуля в нескольких потоках.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="ccomobjectthreadmodel"></a>ккомобжектсреадмодел

Вызывает соответствующие методы модели потоков независимо от используемой потоковой модели.

```
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComObjectThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>Remarks

В зависимости от модели потоков, используемой приложением, имя `typedef` `CComObjectThreadModel` ссылается либо на [ккомсинглесреадмодел](../../atl/reference/ccomsinglethreadmodel-class.md) , либо на [ккоммултисреадмодел](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имена для ссылки на класс критической секции.

> [!NOTE]
> `CComObjectThreadModel` не ссылается на класс [ккоммултисреадмоделнокс](../../atl/reference/ccommultithreadmodelnocs-class.md).

Использование `CComObjectThreadModel` освобождает вас от указания конкретного класса потоковой модели. Независимо от используемой потоковой модели, будут вызываться соответствующие методы.

Помимо `CComObjectThreadModel`, ATL предоставляет имя **typedef** [ккомглобалссреадмодел](#ccomglobalsthreadmodel). Класс, на который ссылается каждое **Определение типа** , зависит от используемой потоковой модели, как показано в следующей таблице.

|typedef|Единая Организация|Потоковое подразделение|Свободная организация потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Используйте `CComObjectThreadModel` в одном классе объекта. Используйте `CComGlobalsThreadModel` в объекте, который либо является глобально доступным для вашей программы, либо для защиты ресурсов модуля в нескольких потоках.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="ccontainedwindow"></a>кконтаинедвиндов

Этот класс является специализацией `CContainedWindowT`.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

### <a name="remarks"></a>Remarks

`CContainedWindow` является специализацией [кконтаинедвиндовт](../../atl/reference/ccontainedwindowt-class.md). Если вы хотите изменить базовый класс или признаки, используйте `CContainedWindowT` напрямую.

##  <a name="cpath"></a>кпас

Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CString`.

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath. h

##  <a name="cpatha"></a>кпаса

Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CStringA`.

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath. h

##  <a name="cpathw"></a>кпасв

Специализация [кпаст](../../atl/reference/cpatht-class.md) с использованием `CStringW`.

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath. h

##  <a name="csimplevalarray"></a>ксимплеваларрай

Представляет массив для хранения простых типов.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Remarks

`CSimpleValArray` предоставляется для создания и управления массивами, содержащими простые типы данных. Это простой #define [ксимплеаррай](../../atl/reference/csimplearray-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлсимпколл. h

##  <a name="lpcurl"></a>лпкурл

Указатель [на постоянный объект](../../atl/reference/curl-class.md) , являющийся константой.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil. h

##  <a name="defaultthreadtraits"></a>дефаултсреадтраитс

Класс признаков потока по умолчанию.

### <a name="syntax"></a>Синтаксис

```
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>Remarks

Если в текущем проекте используется многопоточная CRT, Дефаултсреадтраитс определяется как Кртсреадтраитс. В противном случае используется Win32ThreadTraits.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="lpurl"></a>лпурл

Указатель на [фигурный](../../atl/reference/curl-class.md) объект.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil. h

## <a name="see-also"></a>См. также раздел

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Функции](../../atl/reference/atl-functions.md)<br/>
[Глобальные переменные](../../atl/reference/atl-global-variables.md)<br/>
[Классы и структуры](../../atl/reference/atl-classes.md)<br/>
[Макросы](../../atl/reference/atl-macros.md)
