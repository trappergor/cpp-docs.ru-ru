---
title: Класс CComAutoThreadModule
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 391354c5672cf15c0286491619a13c6005493cfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321069"
---
# <a name="ccomautothreadmodule-class"></a>Класс CComAutoThreadModule

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Параметры

*ThreadAllocator*<br/>
(в) Класс, управляющий выбором потоков. Значение по умолчанию [— CComSimpleThreadAllocator.](../../atl/reference/ccomsimplethreadallocator-class.md)

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Createinstance](#createinstance)|Выбирает поток, а затем создает объект в сопутствующее апартаменты.|
|[GetDefaultThreads](#getdefaultthreads)|(Статик) Динамически вычисляет количество потоков для модуля на основе количества процессоров.|
|[Init](#init)|Создает нити модуля.|
|[Блокировки](#lock)|Приращения блокировки рассчитывают на модуль и на текущий поток.|
|[Разблокировать](#unlock)|Декреты блокировки рассчитывают на модуль и на текущий поток.|

### <a name="data-members"></a>Элементы данных

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[dwThreadID](#dwthreadid)|Содержит идентификатор текущего потока.|
|[m_Allocator](#m_allocator)|Управление выбором потоков.|
|[m_nThreads](#m_nthreads)|Содержит количество потоков в модуле.|
|[m_pApartments](#m_papartments)|Управляет квартирами модуля.|

## <a name="remarks"></a>Remarks

> [!NOTE]
> Этот класс устарел, будучи заменен [классами CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule.](../../atl/reference/catlmodule-class.md) Информация, которая следует для использования со старыми релизами ATL.

`CComAutoThreadModule`получает от [CComModule](../../atl/reference/ccommodule-class.md) для реализации потока пулом, квартира-модель COM сервера для EXEs и Windows услуг. `CComAutoThreadModule`использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления квартирой для каждого потока в модуле.

Извлекайте `CComAutoThreadModule` свой модуль из того момента, когда вы хотите создавать объекты в нескольких квартирах. Необходимо также включить [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макрос в определение класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрику класса.

По умолчанию ATL COM AppWizard (Мастер проекта ATL в Визуальной `CComModule`студии .NET) будет получать ваш модуль из . Для `CComAutoThreadModule`использования измените определение класса. Пример:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[Ccommodule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CComAutoThreadModule::CreateInstance

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Параметры

*pfnCreateInstance*<br/>
(в) Указатель на функцию создателя.

*riid*<br/>
(в) IID запрашиваемого интерфейса.

*ppvObj*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *riid*. Если объект не поддерживает этот интерфейс, *ppvObj* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Выбирает поток, а затем создает объект в сопутствующее апартаменты.

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Remarks

Содержит идентификатор текущего потока.

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Возвращаемое значение

Количество потоков, которые будут созданы в модуле EXE.

### <a name="remarks"></a>Remarks

Эта статическая функция динамически вычисляет максимальное количество потоков для модуля EXE, на основе количества процессоров. По умолчанию это значение возврата передается методу [Init](#init) для создания потоков.

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThreadModule::Init

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Параметры

*P*<br/>
(в) Указатель на массив записей карты объектов.

*H*<br/>
(в) HINSTANCE перешли `DLLMain` к `WinMain`или .

*плибид*<br/>
(в) Указатель на LIBID библиотеки типов, связанных с проектом.

*nThreads*<br/>
(в) Количество создаваемых потоков. По умолчанию *nThreads* — это значение, возвращенное [GetDefaultThreads.](#getdefaultthreads)

### <a name="remarks"></a>Remarks

Инициализирует членов данных и создает количество потоков, указанных *nThreads.*

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a>CComAutoThreadModule::Lock

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
LONG Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Remarks

Выполняет атомное приращение на счете блокировки для модуля и для текущего потока. `CComAutoThreadModule`использует количество блокировок модуля, чтобы определить, имеют ли клиенты доступ к модулю. Подсчет блокировки на текущем потоке используется для статистических целей.

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a>CComAutoThreadModule::m_Allocator

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Remarks

Объект, управляющий выбором потоков. По умолчанию `ThreadAllocator` параметр шаблона класса является [CComSimpleThreadAllocator.](../../atl/reference/ccomsimplethreadallocator-class.md)

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
int m_nThreads;
```

### <a name="remarks"></a>Remarks

Содержит количество потоков в модуле EXE. При вызове [Init](#init) `m_nThreads` устанавливается значение параметра *nThreads.* Сопутствуемая квартира каждого потока управляется объектом [CComApartment.](../../atl/reference/ccomapartment-class.md)

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a>CComAutoThreadModule::m_pApartments

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Remarks

Указывает на массив объектов [CComApartment,](../../atl/reference/ccomapartment-class.md) каждый из которых управляет квартирой в модуле. Количество элементов в массиве основано на [m_nThreads](#m_nthreads) элементе.

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a>CComAutoThreadModule::Разблокировка

По состоянию на ATL 7.0, `CComAutoThreadModule` является устаревшим: см. [ATL Module Classes](../../atl/atl-module-classes.md)

```
LONG Unlock();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

### <a name="remarks"></a>Remarks

Выполняет атомное декретирование на счете блокировки для модуля и для текущего потока. `CComAutoThreadModule`использует количество блокировок модуля, чтобы определить, имеют ли клиенты доступ к модулю. Подсчет блокировки на текущем потоке используется для статистических целей.

Когда количество блокировки модуля достигает нуля, модуль может быть выгружен.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)
