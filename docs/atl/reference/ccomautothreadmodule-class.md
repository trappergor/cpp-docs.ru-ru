---
title: Класс CComAutoThreadModule | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e747386c37e760793ceaa0396f217304cbe621d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022686"
---
# <a name="ccomautothreadmodule-class"></a>Класс CComAutoThreadModule

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Параметры

*ThreadAllocator*<br/>
[in] Класс управления выбора потоков. Значение по умолчанию — [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CreateInstance](#createinstance)|Выбирает поток, а затем создает объект в связанного подразделения.|
|[GetDefaultThreads](#getdefaultthreads)|(Статический) Динамически вычисляет количество потоков для модуля, в зависимости от количества процессоров.|
|[Init](#init)|Создает потоки модуля.|
|[Блокировки](#lock)|Увеличивает счетчик блокировки модуля и в текущем потоке.|
|[разблокировать](#unlock)|Уменьшает счетчик блокировок в модуле и в текущем потоке.|

### <a name="data-members"></a>Элементы данных

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[dwThreadID](#dwthreadid)|Содержит идентификатор текущего потока.|
|[m_Allocator](#m_allocator)|Управляет выделение потока.|
|[m_nThreads](#m_nthreads)|Содержит количество потоков в модуле.|
|[m_pApartments](#m_papartments)|Управляет подразделениями модуля.|

## <a name="remarks"></a>Примечания

> [!NOTE]
>  Этот класс является устаревшим, были заменены [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md) производных классов. Приведенные далее сведения может использоваться с более старых версиях ATL.

`CComAutoThreadModule` является производным от [CComModule](../../atl/reference/ccommodule-class.md) для реализации пула потоков, модель с подразделением COM-сервера для служб exe- и Windows. `CComAutoThreadModule` использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления как подразделение, для каждого потока в модуле.

Наследовать из модуля `CComAutoThreadModule` целесообразно создавать объекты в нескольких подразделениях. Необходимо также включить [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макроса в определении класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса.

По умолчанию мастером приложений COM ATL (мастер проектов ATL в Visual Studio .NET) будет наследовать из модуля `CComModule`. Чтобы использовать `CComAutoThreadModule`, измените определение класса. Пример:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="createinstance"></a>  CComAutoThreadModule::CreateInstance

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Параметры

*pfnCreateInstance*<br/>
[in] Указатель на функцию создателя.

*riid*<br/>
[in] Идентификатор IID запрошенного интерфейса.

*ppvObj*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppvObj* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Выбирает поток, а затем создает объект в связанного подразделения.

##  <a name="dwthreadid"></a>  CComAutoThreadModule::dwThreadID

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Примечания

Содержит идентификатор текущего потока.

##  <a name="getdefaultthreads"></a>  CComAutoThreadModule::GetDefaultThreads

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Число потоков, создаваемых в модуле exe-файла.

### <a name="remarks"></a>Примечания

Эта статическая функция динамически вычисляет максимальное количество потоков для модуля exe-файла, в зависимости от количества процессоров. По умолчанию это значение передается [Init](#init) метод для создания потоков.

##  <a name="init"></a>  CComAutoThreadModule::Init

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на массив элементов объекта map.

*h*<br/>
[in] Передаваемый объект HINSTANCE `DLLMain` или `WinMain`.

*plibid*<br/>
[in] Указатель на идентификатор LIBID библиотеки типов, связанных с проектом.

*nThreads*<br/>
[in] Число потоков должен быть создан. По умолчанию *nThreads* является значение, возвращенное [GetDefaultThreads](#getdefaultthreads).

### <a name="remarks"></a>Примечания

Инициализирует данные-члены и создает число потоков, определяемое *nThreads*.

##  <a name="lock"></a>  CComAutoThreadModule::Lock

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Выполняет шаг atomic счетчик блокировок для модуля, а также для текущего потока. `CComAutoThreadModule` счетчик блокировки модуля используется для определения, ли все клиенты получают доступ к модуля. Число блокировок в текущем потоке используется для статистических целей.

##  <a name="m_allocator"></a>  CComAutoThreadModule::m_Allocator

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Примечания

Объект, управляющий поток выбора. По умолчанию `ThreadAllocator` параметр шаблона класса является [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

##  <a name="m_nthreads"></a>  CComAutoThreadModule::m_nThreads

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
int m_nThreads;
```

### <a name="remarks"></a>Примечания

Содержит количество потоков в модуле exe-файла. Когда [Init](#init) вызове `m_nThreads` присваивается *nThreads* значение параметра. Каждый поток связанного подразделения управляется [CComApartment](../../atl/reference/ccomapartment-class.md) объекта.

##  <a name="m_papartments"></a>  CComAutoThreadModule::m_pApartments

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Примечания

Указывает на массив из [CComApartment](../../atl/reference/ccomapartment-class.md) объектов, каждый из которых управляет подразделение в модуле. Число элементов в массиве основан на [m_nThreads](#m_nthreads) член.

##  <a name="unlock"></a>  CComAutoThreadModule::Unlock

По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Примечания

Выполняет атомарные декремента счетчик блокировок для модуля, а также для текущего потока. `CComAutoThreadModule` счетчик блокировки модуля используется для определения, ли все клиенты получают доступ к модуля. Число блокировок в текущем потоке используется для статистических целей.

Когда счетчик блокировки модуля достигает нуля, модуль может быть выгружен.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Модульные классы](../../atl/atl-module-classes.md)
