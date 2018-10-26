---
title: Определения типов ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9835b8cadb5a24aea130b1e32d919ebb49d20293
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065700"
---
# <a name="atl-typedefs"></a>Определения типов ATL

Active Template Library включает в себя следующие определения типов.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|Определен как определение типа на основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|
|[_ATL_COM_MODULE](#_atl_com_module)|Определен как определение типа на основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|
|[_ATL_MODULE](#_atl_module)|Определен как определение типа на основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|
|[_ATL_WIN_MODULE](#_atl_win_module)|Определен как определение типа на основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|
|[ATL_URL_PORT](#atl_url_port)|Тип, используемый [CUrl](../../atl/reference/curl-class.md) для указания номера порта.|
|[CComDispatchDriver](#ccomdispatchdriver)|Этот класс управляет указателей интерфейса СОМ.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Вызывает методы модели, независимо от модели потоков используется соответствующем потоке.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Вызывает методы модели, независимо от модели потоков используется соответствующем потоке.|
|[CContainedWindow](#ccontainedwindow)|Этот класс является специализацией `CContainedWindowT`.|
|[CPath](#cpath)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CString`.|
|[CPathA](#cpatha)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringA`.|
|[CPathW](#cpathw)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringW`.|
|[CSimpleValArray](#csimplevalarray)|Представляет массив для хранения простых типов.|
|[DefaultThreadTraits](#defaultthreadtraits)|Класс характеристик потока по умолчанию.|
|[LPCURL](#lpcurl)|Указатель на константу [CUrl](../../atl/reference/curl-class.md) объекта.|
|[LPURL](#lpurl)|Указатель на [CUrl](../../atl/reference/curl-class.md) объекта.|

##  <a name="_atl_base_module"></a>  _ATL_BASE_MODULE

Определен как определение типа, в зависимости от _ATL_BASE_MODULE70.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>Примечания

Используется в каждом проекте ATL. На основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

Классы, которые являются частью модульные классы ATL 7.0 являются производными от _ATL_BASE_MODULE структуры.  Дополнительные сведения о модульные классы ATL, см. [классы модулей COM](../../atl/com-modules-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="_atl_com_module"></a>  _ATL_COM_MODULE

Определен как определение типа, в зависимости от _ATL_COM_MODULE70.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>Примечания

Используется в проектах ATL, которые используют функции COM. На основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="_atl_module"></a>  _ATL_MODULE

Определен как определение типа, в зависимости от _ATL_MODULE70.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>Требования

**Заголовок:**

### <a name="remarks"></a>Примечания

На основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

##  <a name="_atl_win_module"></a>  _ATL_WIN_MODULE

Определен как определение типа, в зависимости от _ATL_WIN_MODULE70.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>Примечания

Использовать все проекты ATL, которые используют функции управления окнами. На основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atl_url_port"></a>  ATL_URL_PORT

Тип, используемый [CUrl](curl-class.md) для указания номера порта.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="ccomdispatchdriver"></a>  CComDispatchDriver

Этот класс управляет указателей интерфейса СОМ.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ccomglobalsthreadmodel"></a>  CComGlobalsThreadModel

Вызывает методы модели, независимо от модели потоков используется соответствующем потоке.

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

### <a name="remarks"></a>Примечания

В зависимости от модели потоков, используемых приложением **typedef** имя `CComGlobalsThreadModel` будет содержать либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имен для ссылки на класс критический раздел.

> [!NOTE]
> `CComGlobalsThreadModel` не ссылается на класс [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

С помощью `CComGlobalsThreadModel` освобождает разработчика от указания определенного класса потоковой модели. Независимо от модели потоков используется будет вызываться соответствующие методы.

В дополнение к `CComGlobalsThreadModel`, библиотека ATL предоставляет **typedef** имя [CComObjectThreadModel](#ccomobjectthreadmodel). Класс, который ссылается каждый `typedef` зависит потоковую модель, как показано в следующей таблице:

|typedef|Последовательная обработка|Потоковое|Свободных потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Используйте `CComObjectThreadModel` в пределах одного объекта класса. Используйте `CComGlobalsThreadModel` в объекте, глобально доступные для программы, или если вы хотите защитить модуля ресурсы между несколькими потоками.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ccomobjectthreadmodel"></a>  CComObjectThreadModel

Вызывает методы модели, независимо от модели потоков используется соответствующем потоке.

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

### <a name="remarks"></a>Примечания

В зависимости от модели потоков, используемых приложением `typedef` имя `CComObjectThreadModel` будет содержать либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имен для ссылки на класс критический раздел.

> [!NOTE]
> `CComObjectThreadModel` не ссылается на класс [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).

С помощью `CComObjectThreadModel` освобождает разработчика от указания определенного класса потоковой модели. Независимо от модели потоков используется будет вызываться соответствующие методы.

В дополнение к `CComObjectThreadModel`, библиотека ATL предоставляет **typedef** имя [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Класс, который ссылается каждый **typedef** зависит потоковую модель, как показано в следующей таблице:

|typedef|Последовательная обработка|Потоковое|Свободных потоков|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

Используйте `CComObjectThreadModel` в пределах одного объекта класса. Используйте `CComGlobalsThreadModel` в объекте, либо глобально доступной, программу или когда необходимо обеспечить защиту ресурсов модуля в нескольких потоках.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ccontainedwindow"></a>  CContainedWindow

Этот класс является специализацией `CContainedWindowT`.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

### <a name="remarks"></a>Примечания

`CContainedWindow` является специализацией [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Если вы хотите изменить базовый класс или признаков, используйте `CContainedWindowT` напрямую.

##  <a name="cpath"></a>  CPath

Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CString`.

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

##  <a name="cpatha"></a>  CPathA

Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringA`.

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

##  <a name="cpathw"></a>  CPathW

Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringW`.

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>Требования

**Заголовок:** atlpath.h

##  <a name="csimplevalarray"></a>  CSimpleValArray

Представляет массив для хранения простых типов.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>Примечания

`CSimpleValArray` предоставляется для создания и управления массивы, содержащие простые типы данных. Это простой #define из [CSimpleArray](../../atl/reference/csimplearray-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

##  <a name="lpcurl"></a>  LPCURL

Указатель на константу [CUrl](../../atl/reference/curl-class.md) объекта.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="defaultthreadtraits"></a>  DefaultThreadTraits

Класс характеристик потока по умолчанию.

### <a name="syntax"></a>Синтаксис

```
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>Примечания

Если в текущем проекте используется многопоточные CRT, DefaultThreadTraits определяется как CRTThreadTraits. В противном случае используется Win32ThreadTraits.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="lpurl"></a>  LPURL

Указатель на [CUrl](../../atl/reference/curl-class.md) объекта.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="see-also"></a>См. также

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Функции](../../atl/reference/atl-functions.md)<br/>
[Глобальные переменные](../../atl/reference/atl-global-variables.md)<br/>
[Классы и структуры](../../atl/reference/atl-classes.md)<br/>
[Макросы](../../atl/reference/atl-macros.md)
