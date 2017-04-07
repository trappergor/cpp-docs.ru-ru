---
title: "Класс CComAutoThreadModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 07aaf6dc7029452fa6822c5f5f1ae09b724ddc8b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautothreadmodule-class"></a>Класс CComAutoThreadModule
Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>Параметры  
 `ThreadAllocator`  
 [in] Класс выбора потока управления. Значение по умолчанию — [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|Выбирает поток и затем создает объект в связанный подразделении.|  
|[GetDefaultThreads](#getdefaultthreads)|(Статический) Динамически вычисляет количество потоков для модуля, в зависимости от количества процессоров.|  
|[Init](#init)|Создает потоки модуля.|  
|[Блокировка](#lock)|Увеличивает счетчик блокировки модуля и в текущем потоке.|  
|[Разблокировать](#unlock)|Уменьшает на единицу счетчик блокировок на модуль и в текущем потоке.|  
  
### <a name="data-members"></a>Элементы данных  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|Содержит идентификатор текущего потока.|  
|[m_Allocator](#m_allocator)|Управляет выбора потоков.|  
|[m_nThreads](#m_nthreads)|Содержит количество потоков в модуле.|  
|[m_pApartments](#m_papartments)|Управляет подразделениями модуля.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот класс устарел, были заменены [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md) производных классов. Ниже приведена для использования с более старые версии библиотеки ATL.  
  
 `CComAutoThreadModule`является производным от [CComModule](../../atl/reference/ccommodule-class.md) для реализации пула потоков, модели подразделения COM-сервера для EXE-файлов и служб Windows. `CComAutoThreadModule`использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления подразделениями для каждого потока в модуле.  
  
 Наследовать от вашего модуля `CComAutoThreadModule` используется для создания объектов в нескольких подразделениях. Необходимо также включить [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) макрос в определении класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса.  
  
 По умолчанию мастер приложений COM ATL (мастер проектов ATL в Visual Studio .NET) будет наследовать от вашего модуля `CComModule`. Для использования `CComAutoThreadModule`, измените определение класса. Пример:  
  
 [!code-cpp[NVC_ATL_AxHost&#2;](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
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
  
##  <a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 *pfnCreateInstance*  
 [in] Указатель на функцию, создатель.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса.  
  
 `ppvObj`  
 [out] Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppvObj` имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Выбирает поток и затем создает объект в связанный подразделении.  
  
##  <a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит идентификатор текущего потока.  
  
##  <a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число потоков, создаваемых в модуле exe-файла.  
  
### <a name="remarks"></a>Примечания  
 Эта статическая функция динамически вычисляет максимальное количество потоков для модуля exe-файла, в зависимости от количества процессоров. По умолчанию это значение передается [Init](#init) метод для создания потоков.  
  
##  <a name="init"></a>CComAutoThreadModule::Init  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на массив записей объекта карты.  
  
 `h`  
 [in] `HINSTANCE` Переданы **DLLMain** или `WinMain`.  
  
 `plibid`  
 [in] Указатель на идентификатор LIBID библиотеки типов, связанных с проектом.  
  
 `nThreads`  
 [in] Число потоков, создаваемых. По умолчанию `nThreads` является значение, возвращенное [GetDefaultThreads](#getdefaultthreads).  
  
### <a name="remarks"></a>Примечания  
 Инициализирует элементы данных и создает указанное число потоков `nThreads`.  
  
##  <a name="lock"></a>CComAutoThreadModule::Lock  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Выполняет атомарные приращение счетчика блокировок для модуля и для текущего потока. `CComAutoThreadModule`счетчик блокировки модуля используется для определения, является ли все клиенты получают доступ к модуль. Число блокировок для текущего потока используется для статистических целей.  
  
##  <a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>Примечания  
 Объект, выбор потока управления. По умолчанию `ThreadAllocator` параметр шаблона класса [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
##  <a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит количество потоков в модуле exe-файла. Когда [Init](#init) вызывается, `m_nThreads` присвоено `nThreads` значение параметра. Каждый поток связанного подразделения осуществляется с помощью [CComApartment](../../atl/reference/ccomapartment-class.md) объекта.  
  
##  <a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>Примечания  
 Указывает массив [CComApartment](../../atl/reference/ccomapartment-class.md) объектов, каждый из которых управляет подразделение в модуле. Число элементов в массиве основана на [m_nThreads](#m_nthreads) член.  
  
##  <a name="unlock"></a>CComAutoThreadModule::Unlock  
 Начиная с ATL 7.0 `CComAutoThreadModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 Выполняет атомарные декремент счетчика блокировок для модуля и для текущего потока. `CComAutoThreadModule`счетчик блокировки модуля используется для определения, является ли все клиенты получают доступ к модуль. Число блокировок для текущего потока используется для статистических целей.  
  
 Когда счетчик блокировки модуля достигает нуля, модуль может быть выгружен.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)

