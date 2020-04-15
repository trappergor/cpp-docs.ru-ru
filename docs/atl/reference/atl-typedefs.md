---
title: Определения типов ATL
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
ms.openlocfilehash: 5548bee36ac52dbd6add31241714b0404289be45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319193"
---
# <a name="atl-typedefs"></a>Определения типов ATL

Библиотека Active Template содержит следующие типы.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|Определяется как typedef на основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|
|[_ATL_COM_MODULE](#_atl_com_module)|Определяется как typedef на основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|
|[_ATL_MODULE](#_atl_module)|Определяется как typedef на основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|
|[_ATL_WIN_MODULE](#_atl_win_module)|Определяется как typedef на основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|
|[ATL_URL_PORT](#atl_url_port)|Тип, используемый [CUrl](../../atl/reference/curl-class.md) для указания номера порта.|
|[CComDispatchDriver](#ccomdispatchdriver)|Этот класс управляет указателями интерфейсов COM.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Вызывает соответствующие методы модели потоков, независимо от используемой модели потоков.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Вызывает соответствующие методы модели потоков, независимо от используемой модели потоков.|
|[CContainedWindow](#ccontainedwindow)|Этот класс является специализацией `CContainedWindowT`.|
|[CPath](#cpath)|Специализация [CPathT](../../atl/reference/cpatht-class.md) `CString`с использованием .|
|[CPathA](#cpatha)|Специализация [CPathT](../../atl/reference/cpatht-class.md) `CStringA`с использованием .|
|[CPathW](#cpathw)|Специализация [CPathT](../../atl/reference/cpatht-class.md) `CStringW`с использованием .|
|[CSimpleValArray](#csimplevalarray)|Представляет массив для хранения простых типов.|
|[DefaultThreadTraits](#defaultthreadtraits)|Класс признаков потока по умолчанию.|
|[LPCURL](#lpcurl)|Указатель на постоянный объект [CUrl.](../../atl/reference/curl-class.md)|
|[ЛТУРЛ](#lpurl)|Указатель на объект [CUrl.](../../atl/reference/curl-class.md)|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE

Определяется как typedef на основе _ATL_BASE_MODULE70.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Remarks

Используется в каждом проекте ATL. По данным [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

Классы, входят в классы модулей ATL 7.0, происходят из структуры _ATL_BASE_MODULE.  Для получения дополнительной информации о классах модулей ATL, обратитесь к [классам модулей COM](../../atl/com-modules-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE

Определяется как typedef на основе _ATL_COM_MODULE70.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Remarks

Используется проектами ATL, которые используют функции COM. По данным [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="_atl_module"></a><a name="_atl_module"></a>_ATL_MODULE

Определяется как typedef на основе _ATL_MODULE70.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>Требования

**Заголовка:**

### <a name="remarks"></a>Remarks

По материалам [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE

Определяется как typedef на основе _ATL_WIN_MODULE70.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Remarks

Используется любыми проектами ATL, которые используют функции оконного окна. По _ATL_WIN_MODULE70 [.](../../atl/reference/atl-win-module70-structure.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atl_url_port"></a><a name="atl_url_port"></a>ATL_URL_PORT

Тип, используемый [CUrl](curl-class.md) для указания номера порта.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatchDriver

Этот класс управляет указателями интерфейсов COM.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel

Вызывает соответствующие методы модели потоков, независимо от используемой модели потоков.

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

В зависимости от модели потоков, используемой вашим `CComGlobalsThreadModel` приложением, ссылки на имя **typedef** of либо [CComSingleThreadModel,](../../atl/reference/ccomsinglethreadmodel-class.md) либо [CComMultiThreadModel.](../../atl/reference/ccommultithreadmodel-class.md) Эти классы `typedef` предоставляют дополнительные имена для ссылки на критический класс раздела.

> [!NOTE]
> `CComGlobalsThreadModel`не ссылается на класс [CcommultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Использование `CComGlobalsThreadModel` освобождает вас от указания определенного класса модели потоков. Независимо от используемой модели потоков, будут вызываться соответствующие методы.

В дополнение `CComGlobalsThreadModel`к, ATL предоставляет **typedef** имя [CComObjectThreadModel](#ccomobjectthreadmodel). Класс, на который `typedef` ссылается каждый из них, зависит от используемой модели потоков, как показано в следующей таблице:

|typedef|Одноразовая резьба|Квартира резьбы|Бесплатное резьбовое|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

СЗ `CComSingleThreadModel`; МЗ`CComMultiThreadModel`

Используйте `CComObjectThreadModel` в одном классе объектов. Используйте `CComGlobalsThreadModel` объект, который глобально доступен для вашей программы, или когда вы хотите защитить ресурсы модуля через несколько потоков.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObjectThreadModel

Вызывает соответствующие методы модели потоков, независимо от используемой модели потоков.

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

В зависимости от модели потоков, используемой вашим приложением, `typedef` `CComObjectThreadModel` имя ссылается либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Эти классы `typedef` предоставляют дополнительные имена для ссылки на критический класс раздела.

> [!NOTE]
> `CComObjectThreadModel`не ссылается на класс [CcommultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

Использование `CComObjectThreadModel` освобождает вас от указания определенного класса модели потоков. Независимо от используемой модели потоков, будут вызываться соответствующие методы.

В дополнение `CComObjectThreadModel`к, ATL предоставляет **typedef** имя [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Класс, на который ссылается каждый **тип,** зависит от используемой модели потоков, как показано в следующей таблице:

|typedef|Одноразовая резьба|Квартира резьбы|Бесплатное резьбовое|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

СЗ `CComSingleThreadModel`; МЗ`CComMultiThreadModel`

Используйте `CComObjectThreadModel` в одном классе объектов. Используйте `CComGlobalsThreadModel` объект, который либо глобально доступен для вашей программы, либо когда требуется защитить ресурсы модуля в нескольких потоках.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow

Этот класс является специализацией `CContainedWindowT`.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

### <a name="remarks"></a>Remarks

`CContainedWindow`является специализацией [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Если вы хотите изменить базовый класс `CContainedWindowT` или черты, используйте напрямую.

## <a name="cpath"></a><a name="cpath"></a>CPath

Специализация [CPathT](../../atl/reference/cpatht-class.md) `CString`с использованием .

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

## <a name="cpatha"></a><a name="cpatha"></a>CPathA

Специализация [CPathT](../../atl/reference/cpatht-class.md) `CStringA`с использованием .

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

## <a name="cpathw"></a><a name="cpathw"></a>CPathW

Специализация [CPathT](../../atl/reference/cpatht-class.md) `CStringW`с использованием .

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray

Представляет массив для хранения простых типов.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Remarks

`CSimpleValArray`предусмотрено для создания и управления массивами, содержащими простые типы данных. Это простой #define [CSimpleArray](../../atl/reference/csimplearray-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="lpcurl"></a><a name="lpcurl"></a>LPCURL

Указатель на постоянный объект [CUrl.](../../atl/reference/curl-class.md)

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a>DefaultThreadTraits

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

Если в текущем проекте используется многопоточный CRT, defaultThreadTraits определяется как CRTThreadTraits. В противном случае используется Win32ThreadTraits.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="lpurl"></a><a name="lpurl"></a>ЛТУРЛ

Указатель на объект [CUrl.](../../atl/reference/curl-class.md)

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="see-also"></a>См. также раздел

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Функции](../../atl/reference/atl-functions.md)<br/>
[Глобальные переменные](../../atl/reference/atl-global-variables.md)<br/>
[Классы и структуры](../../atl/reference/atl-classes.md)<br/>
[Макросы](../../atl/reference/atl-macros.md)
