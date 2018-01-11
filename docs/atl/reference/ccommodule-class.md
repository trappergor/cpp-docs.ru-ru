---
title: "CComModule-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
dev_langs: C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b86e1f082b7be844afe3b1a84d182d1c722f500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccommodule-class"></a>CComModule-класс
Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Создает объект для указанного идентификатора CLSID. Для DLL.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Возвращает `m_hInst`.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Возвращает `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Возвращает `m_hInstTypeLib`.|  
|[CComModule::Init](#init)|Инициализирует элементы данных.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Вводит регистрации стандартный класс объекта в системном реестре.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса. Для EXE-файлов только.|  
|[CComModule::RegisterServer](#registerserver)|Обновляет системного реестра для каждого объекта в карте объектов.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Регистрирует библиотеку типов.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса. Для EXE-файлов только.|  
|[CComModule::Term](#term)|Освобождает данные-члены.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Удаляет регистрацию стандартный класс объекта из системного реестра.|  
|[CComModule::UnregisterServer](#unregisterserver)|Отменяет регистрацию каждый объект в карте объектов.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Регистрирует или отменяет регистрацию регистрации стандартный класс объекта.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Статически ссылки на компонент реестра ATL. Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Обеспечивает синхронизированный доступ к сведениям объекта карты.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Обеспечивает синхронизированного доступа к информации о библиотеке типов.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Обеспечивает синхронизированного доступа для окна сведений о классах и статические данные, используемые при создании окна.|  
|[CComModule::m_hInst](#m_hinst)|Содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstResource](#m_hinstresource)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Указывает объект карты, обслуживается экземпляра модуля.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот класс является устаревшим, и теперь использовать мастера формирования кода ATL [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md) производных классов. В разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительной информации. Приведенные далее сведения предназначен для использования с приложениями, созданных с помощью более старых версий библиотеки ATL. `CComModule`по-прежнему частью ATL для обеспечения обратной возможностей.  
  
 `CComModule`реализует COM-модуля сервера, что позволяет клиенту получить доступ к компонентам модуля. `CComModule`поддерживает DLL (внутрипроцессные) и EXE-файла (local) модулей.  
  
 Объект `CComModule` экземпляр использует схему объекта, чтобы обслуживать набор определений объектов класса. На этой карте объекта реализуется как массив `_ATL_OBJMAP_ENTRY` структуры и содержит информацию для:  
  
-   Ввод и удаление описания объектов в системном реестре.  
  
-   Создание экземпляров объектов с помощью фабрики класса.  
  
-   Установление связи между клиентом и корневой объект в компоненте.  
  
-   Выполнение управления временем существования объектов классов.  
  
 При запуске мастер приложений COM ATL, мастер автоматически создает `_Module`, глобальный экземпляр класса `CComModule` или класс, производный от него. Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
 В дополнение к `CComModule`, библиотека ATL предоставляет [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), который реализует модуль модели для EXE-файлов и служб Windows. Является производным от своего модуля `CComAutoThreadModule` при необходимости создавать объекты в нескольких подразделениях.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="getclassobject"></a>CComModule::GetClassObject  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rclsid`  
 [in] CLSID объекта должен быть создан.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса.  
  
 `ppv`  
 [out] Указатель на указатель на интерфейс, определяемый `riid`. Если объект не поддерживает этот интерфейс `ppv` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Создает объект для указанного идентификатора CLSID и возвращает указатель интерфейса на этот объект.  
  
 `GetClassObject`доступен только для DLL-библиотеки.  
  
##  <a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Определение этого модуля.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInst](#m_hinst) члена данных.  
  
##  <a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HINSTANCE`.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstResource](#m_hinstresource) члена данных.  
  
##  <a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HINSTANCE`.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstTypeLib](#m_hinsttypelib) члена данных.  
  
##  <a name="init"></a>CComModule::Init  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 [in] Указатель на массив записей объекта карты.  
  
 `h`  
 [in] `HINSTANCE` Передаваемый **DLLMain** или `WinMain`.  
  
 `plibid`  
 [in] Указатель на идентификатор LIBID библиотеки типов, связанные с проектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует все члены данных.  
  
##  <a name="m_csobjmap"></a>CComModule::m_csObjMap  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к схеме объекта.  
  
##  <a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к библиотеке типов.  
  
##  <a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к информации о класса окна и статические данные, используемые при создании окна.  
  
##  <a name="m_hinst"></a>CComModule::m_hInst  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInst` в дескриптор, переданный **DLLMain** или `WinMain`.  
  
##  <a name="m_hinstresource"></a>CComModule::m_hInstResource  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstResource` в дескриптор, переданный **DLLMain** или `WinMain`. Можно явно задать `m_hInstResource` дескриптор ресурса.  
  
 [GetResourceInstance](#getresourceinstance) метод возвращает дескриптор, хранящиеся в `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstTypeLib` в дескриптор, переданный **DLLMain** или `WinMain`. Можно явно задать `m_hInstTypeLib` для обработки в библиотеку типов.  
  
 [GetTypeLibInstance](#gettypelibinstance) метод возвращает дескриптор, хранящиеся в `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>CComModule::m_pObjMap  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Указывает объект карты, обслуживается экземпляра модуля.  
  
##  <a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] CLSID регистрируемого объекта.  
  
 `lpszProgID`  
 [in] Идентификатор ProgID, связанный с объектом.  
  
 `lpszVerIndProgID`  
 [in] Идентификатор ProgID зависят от версии, связанный с объектом.  
  
 `nDescID`  
 [in] Идентификатор строкового ресурса для описания объекта.  
  
 `dwFlags`  
 [in] Указывает, что потоковая модель для ввода в реестре. Возможными значениями являются **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Вводит регистрации стандартный класс объекта в системном реестре.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы метода `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwClsContext`  
 [in] Указывает контекст, в котором будет выполняться объекта класса. Возможными значениями являются **CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, или **CLSCTX_LOCAL_SERVER**. Описание этих значений см. в разделе [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) в Windows SDK.  
  
 `dwFlags`  
 [in] Определяет типы подключения к такому объекту класса. Возможными значениями являются **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, или **REGCLS_MULTI_SEPARATE**. Описание этих значений см. в разделе [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Регистрирует объект класса exe-файла с OLE, поэтому другие приложения могли подключиться к нему. Этот метод доступен только для EXE-файлов.  
  
##  <a name="registerserver"></a>CComModule::RegisterServer  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 [in] Указывает, будет ли зарегистрирована библиотека типов. Значение по умолчанию — **FALSE**.  
  
 `pCLSID`  
 [in] Указывает идентификатор CLSID регистрируемого объекта. Если **NULL** (значение по умолчанию), будут зарегистрированы всех объектов в карте объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от `pCLSID` параметра обновляет системного реестра для одного класса объекта или для всех объектов в карте объектов.  
  
 Если `bRegTypeLib` — **TRUE**, также будут обновлены сведения о библиотеке типов.  
  
 В разделе [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) сведения о том, как добавить запись в карте объектов.  
  
 `RegisterServer`будет вызываться автоматически **DLLRegisterServer** для библиотеки DLL или с помощью `WinMain` для EXE-файла запустите с **/regserver** параметр командной строки.  
  
##  <a name="registertypelib"></a>CComModule::RegisterTypeLib  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 [in] Строка в формате `"\\N"`, где `N` — это целочисленный индекс ресурса TYPELIB.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Добавляет сведения о библиотеке типов в системный реестр.  
  
 Если экземпляра модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов можно использовать второй версии данного метода.  
  
##  <a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект класса. Этот метод доступен только для EXE-файлов.  
  
##  <a name="term"></a>CComModule::Term  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных.  
  
##  <a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] Идентификатор CLSID объекта, для отмены регистрации.  
  
 `lpszProgID`  
 [in] Идентификатор ProgID, связанный с объектом.  
  
 `lpszVerIndProgID`  
 [in] Идентификатор ProgID зависят от версии, связанный с объектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет регистрацию стандартный класс объекта из системного реестра.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы метода `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>CComModule::UnregisterServer  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Параметры  
 `bUnRegTypeLib`  
 Если **TRUE**, также отменяется библиотеки типов.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если **NULL** (значение по умолчанию), все объекты в схеме объекта будет отменена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от `pCLSID` параметр отменяет регистрацию объектов одного класса или всех объектов в карте объектов.  
  
 `UnregisterServer`будет вызываться автоматически **DLLUnregisterServer** для библиотеки DLL или с помощью `WinMain` для EXE-файла запустите с **/unregserver** параметр командной строки.  
  
 В разделе [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) сведения о том, как добавить запись в карте объектов.  
  
##  <a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Код CLSID объекта зарегистрирован или отменять регистрацию.  
  
 `lpszProgID`  
 Идентификатор ProgID, связанный с объектом.  
  
 `lpszVerIndProgID`  
 Идентификатор ProgID зависят от версии, связанный с объектом.  
  
 `nDescID`  
 Идентификатор строкового ресурса для описания объекта.  
  
 `szDesc`  
 Строка, содержащая описание объекта.  
  
 `dwFlags`  
 Указывает, что потоковая модель для ввода в реестре. Возможными значениями являются **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
 `bRegister`  
 Указывает, зарегистрировано ли объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если `bRegister` — **TRUE**, этот метод вводит регистрации стандартный класс объекта в системном реестре.  
  
 Если `bRegister` — **FALSE**, он удаляет регистрацию объекта.  
  
 В зависимости от значения `bRegister`, `UpdateRegistryClass` вызывает метод [RegisterClassHelper](#registerclasshelper) или [UnregisterClassHelper](#unregisterclasshelper).  
  
 Указав [DECLARE_REGISTRY](registry-macros.md#declare_registry) макрос, `UpdateRegistryClass` будет вызываться автоматически, при обработке в карте объектов.  
  
##  <a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
virtual HRESULT UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszRes`  
 [in] Имя ресурса.  
  
 `nResID`  
 [in] Идентификатор ресурса.  
  
 `bRegister`  
 [in] Указывает, зарегистрировано ли объект.  
  
 `pMapEntries`  
 [in] Указатель на карту замены хранения значений, связанных с подстановочные параметры этого сценария. Автоматически использует ATL `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. заметки подробные сведения. В противном случае используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Запускает скрипт, содержащийся в ресурс, указанный параметром `lpszRes` или `nResID`.  
  
 Если `bRegister` — **TRUE**, этот метод регистрирует объект в системном реестре; в противном случае удаляет регистрацию объекта.  
  
 Указав [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) макрос, `UpdateRegistryFromResourceD` будет вызываться автоматически, при обработке в карте объектов.  
  
> [!NOTE]
>  Чтобы заменить значения замены во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** пару структур, где каждая запись содержит заполнитель переменной со значением, замените заполнитель во время выполнения. Затем вызовите `UpdateRegistryFromResourceD`, передавая массив для `pMapEntries` параметра. Это добавляет все значения замены **_ATL_REGMAP_ENTRIES** структуры карту замены регистратора.  
  
> [!NOTE]
>  Статическое связывание компонент реестра ATL (регистратор), в разделе [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
virtual HRESULT UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszRes`  
 [in] Имя ресурса.  
  
 `nResID`  
 [in] Идентификатор ресурса.  
  
 `bRegister`  
 [in] Указывает, зарегистрировано ли файл скрипта ресурсов.  
  
 `pMapEntries`  
 [in] Указатель на карту замены хранения значений, связанных с подстановочные параметры этого сценария. Автоматически использует ATL `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. заметки подробные сведения. В противном случае используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [UpdateRegistryFromResourceD](#updateregistryfromresourced) за исключением `UpdateRegistryFromResourceS` создает статическую ссылку на компонент реестра ATL (регистратор).  
  
 `UpdateRegistryFromResourceS`будет вызываться автоматически при обработке карте объекта условии добавления `#define _ATL_STATIC_REGISTRY` ваш файл stdafx.h.  
  
> [!NOTE]
>  Чтобы заменить значения замены во время выполнения, не указывайте [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** пару структур, где каждая запись содержит заполнитель переменной со значением, замените заполнитель во время выполнения. Затем вызовите `UpdateRegistryFromResourceS`, передавая массив для `pMapEntries` параметра. Это добавляет все значения замены **_ATL_REGMAP_ENTRIES** структуры карту замены регистратора.  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
