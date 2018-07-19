---
title: Класс CComModule | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae4218d6c6446554d5fb45d680588127ec3e0ee
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883096"
---
# <a name="ccommodule-class"></a>CComModule-класс
По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
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
|[CComModule::GetClassObject](#getclassobject)|Создает объект с заданным идентификатором CLSID. Для DLL.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Возвращает `m_hInst`.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Возвращает `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Возвращает `m_hInstTypeLib`.|  
|[Выполнения](#init)|Инициализирует данные-члены.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Вводит регистрации стандартный класс объекта в системном реестре.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса. EXE-файлами только.|  
|[CComModule::RegisterServer](#registerserver)|Обновляет системного реестра для каждого объекта в карте объектов.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Регистрирует библиотеку типов.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса. EXE-файлами только.|  
|[CComModule::Term](#term)|Освобождает данные-члены.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Удаляет регистрацию стандартный класс объекта, из системного реестра.|  
|[CComModule::UnregisterServer](#unregisterserver)|Отменяет регистрацию каждого объекта в карте объектов.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Регистрирует или отменяет регистрацию объекта стандартный класс регистрации.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Выполняется скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Статически ссылки на компонент реестра ATL. Выполняется скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Гарантирует синхронизированного доступа к сведениям объекта карты.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Гарантирует синхронизированного доступа к информации о библиотеке типов.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Гарантирует синхронизированного доступа к сведениям о классе окна и статические данные, использованные при создании окна.|  
|[CComModule::m_hInst](#m_hinst)|Содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstResource](#m_hinstresource)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Указывает на карте объектов, поддерживаемых экземпляром модуля.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот класс является устаревшим, и теперь использование мастеров создания кода ATL [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md) производных классов. См. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) Дополнительные сведения. Приведенные далее сведения предназначен для использования с приложениями, созданных с помощью более старых версиях ATL. `CComModule` остается частью ATL для обеспечения обратной возможностей.  
  
 `CComModule` реализует COM-модуля сервера, что позволяет клиенту получить доступ к компонентам модуля. `CComModule` поддерживает оба модуля (local) exe-файла, так и библиотеки DLL (внутрипроцессный).  
  
 Объект `CComModule` экземпляр использует схему объекта набор определений классов объектов. Эта карта объект реализуется как массив `_ATL_OBJMAP_ENTRY` структуры, который содержит сведения для:  
  
-   Ввод и удаление описания объектов в системном реестре.  
  
-   Создание экземпляров объектов с помощью фабрики класса.  
  
-   Установка связи между клиентом и корневой объект в компоненте.  
  
-   Выполнение управление временем существования объектов классов.  
  
 При запуске мастером приложений COM ATL, мастер автоматически создает `_Module`, глобальный экземпляр `CComModule` или класс, производный от него. Дополнительные сведения о мастере проекта ATL, см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).  
  
 В дополнение к `CComModule`, библиотека ATL предоставляет [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), который реализует модуль модель с подразделением служб exe- и Windows. Наследовать из модуля `CComAutoThreadModule` целесообразно создавать объекты в нескольких подразделениях.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="getclassobject"></a>  CComModule::GetClassObject  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *rclsid*  
 [in] CLSID создаваемого объекта.  
  
 *riid*  
 [in] Идентификатор IID запрошенного интерфейса.  
  
 *ppv*  
 [out] Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppv* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.  
  
 `GetClassObject` доступна только на библиотеки DLL.  
  
##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HINSTANCE, определяющий этот модуль.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInst](#m_hinst) данные-член.  
  
##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HINSTANCE.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstResource](#m_hinstresource) данные-член.  
  
##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HINSTANCE.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstTypeLib](#m_hinsttypelib) данные-член.  
  
##  <a name="init"></a>  Выполнения  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 [in] Указатель на массив элементов объекта map.  
  
 *h*  
 [in] Передаваемый объект HINSTANCE `DLLMain` или `WinMain`.  
  
 *plibid*  
 [in] Указатель на идентификатор LIBID библиотеки типов, связанных с проектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует все члены данных.  
  
##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Гарантирует синхронизированного доступа к схеме объекта.  
  
##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Примечания  
 Гарантирует синхронизированного доступа к библиотеке типов.  
  
##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Примечания  
 Гарантирует синхронизированного доступа к информации о классе окна и статические данные, использованные при создании окна.  
  
##  <a name="m_hinst"></a>  CComModule::m_hInst  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInst` к дескриптору, передаваемое `DLLMain` или `WinMain`.  
  
##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstResource` к дескриптору, передаваемое `DLLMain` или `WinMain`. Можно явно задать `m_hInstResource` на дескриптор для ресурса.  
  
 [GetResourceInstance](#getresourceinstance) метод возвращает дескриптор, хранящиеся в `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstTypeLib` к дескриптору, передаваемое `DLLMain` или `WinMain`. Можно явно задать `m_hInstTypeLib` для обработки в библиотеку типов.  
  
 [GetTypeLibInstance](#gettypelibinstance) метод возвращает дескриптор, хранящиеся в `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Указывает на карте объектов, поддерживаемых экземпляром модуля.  
  
##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *CLSID*  
 [in] CLSID объекта для регистрации.  
  
 *lpszProgID*  
 [in] Идентификатор ProgID, связанный с объектом.  
  
 *lpszVerIndProgID*  
 [in] Идентификатор ProgID независящим от версии, связанный с объектом.  
  
 *nDescID*  
 [in] Идентификатор строкового ресурса описания объекта.  
  
 *dwFlags*  
 [in] Указывает потоковую модель, чтобы ввести в реестре. Возможные значения: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Вводит регистрации стандартный класс объекта в системном реестре.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы методов `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwClsContext*  
 [in] Определяет контекст, в котором будет выполняться объект класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. Описание этих значений, см. в разделе [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) в пакете Windows SDK.  
  
 *dwFlags*  
 [in] Определяет типы подключения к объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. Описание этих значений, см. в разделе [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Регистрирует объект класса exe-файла с OLE, поэтому другие приложения могли подключиться к нему. Этот метод доступен только для EXE-файлы.  
  
##  <a name="registerserver"></a>  CComModule::RegisterServer  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bRegTypeLib*  
 [in] Указывает, будет ли зарегистрирована библиотека типов. Значение по умолчанию — FALSE.  
  
 *pCLSID*  
 [in] Указывает идентификатор CLSID объекта для регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет зарегистрировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от *pCLSID* параметра, обновляет системного реестра для одного класса объекта или для всех объектов в карте объектов.  
  
 Если *bRegTypeLib* имеет значение TRUE, также будут обновлены сведения о библиотеке типов.  
  
 См. в разделе [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) сведения о том, как добавить запись в карте объектов.  
  
 `RegisterServer` будет вызван автоматически по `DLLRegisterServer` для библиотеки DLL или с помощью `WinMain` для запуска с помощью EXE `/RegServer` параметр командной строки.  
  
##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszIndex*  
 [in] Строка в формате `"\\N"`, где `N` — это целочисленный индекс ресурса библиотеки ТИПОВ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Добавляет сведения о библиотеке типов в системный реестр.  
  
 Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов следует использовать второй версии этого метода.  
  
##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект класса. Этот метод доступен только для EXE-файлы.  
  
##  <a name="term"></a>  CComModule::Term  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных.  
  
##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Параметры  
 *CLSID*  
 [in] CLSID объекта для отмены регистрации.  
  
 *lpszProgID*  
 [in] Идентификатор ProgID, связанный с объектом.  
  
 *lpszVerIndProgID*  
 [in] Идентификатор ProgID независящим от версии, связанный с объектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет регистрацию стандартный класс объекта, из системного реестра.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы методов `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>  CComModule::UnregisterServer  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Параметры  
 *bUnRegTypeLib*  
 Значение TRUE, если библиотека типов также отменяется.  
  
 *pCLSID*  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет отменена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от *pCLSID* параметра, отменяет регистрацию объекта класса одной или всех объектов в карте объектов.  
  
 `UnregisterServer` будет вызван автоматически по `DLLUnregisterServer` для библиотеки DLL или с помощью `WinMain` для запуска с помощью EXE `/UnregServer` параметр командной строки.  
  
 См. в разделе [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) сведения о том, как добавить запись в карте объектов.  
  
##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
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
 *CLSID*  
 CLSID объекта регистрировать или отменять регистрацию.  
  
 *lpszProgID*  
 Идентификатор ProgID, связанный с объектом.  
  
 *lpszVerIndProgID*  
 Идентификатор ProgID независящим от версии, связанный с объектом.  
  
 *nDescID*  
 Идентификатор строкового ресурса описания объекта.  
  
 *szDesc*  
 Строка, содержащая описание объекта.  
  
 *dwFlags*  
 Указывает потоковую модель, чтобы ввести в реестре. Возможные значения: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.  
  
 *bЗарегистрируйтесь участия*  
 Указывает, является ли объект должен быть зарегистрирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если *bЗарегистрируйтесь участия* имеет значение TRUE, этот метод вводит регистрации стандартный класс объекта в системном реестре.  
  
 Если *bЗарегистрируйтесь участия* имеет значение FALSE, он удаляет регистрацию объекта.  
  
 В зависимости от значения *bЗарегистрируйтесь участия*, `UpdateRegistryClass` голосовой звонок [RegisterClassHelper](#registerclasshelper) или [UnregisterClassHelper](#unregisterclasshelper).  
  
 Путем указания [DECLARE_REGISTRY](registry-macros.md#declare_registry) макрос, `UpdateRegistryClass` будет вызываться автоматически, при обработке объекта карты.  
  
##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
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
 *lpszRes*  
 [in] Имя ресурса.  
  
 *nResID*  
 [in] Идентификатор ресурса.  
  
 *bЗарегистрируйтесь участия*  
 [in] Указывает, является ли объект должен быть зарегистрирован.  
  
 *pMapEntries*  
 [in] Указатель на карте замены хранения значений, связанных с подстановочных параметров сценария. ATL автоматически использует `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. в разделе "Примечания" Дополнительные сведения. В противном случае используйте значение по умолчанию NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Выполняется скрипт, содержащийся в ресурс, заданный параметром *lpszRes* или *nResID*.  
  
 Если *bЗарегистрируйтесь участия* имеет значение TRUE, этот метод регистрирует объект в системном реестре; в противном случае он отменяет регистрацию объекта.  
  
 Путем указания [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) макрос, `UpdateRegistryFromResourceD` будет вызываться автоматически, при обработке объекта карты.  
  
> [!NOTE]
>  Чтобы заменить замены значения во время выполнения, не указывайте макрос DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структуры, где каждая запись содержит переменной заполнитель в паре со значением для замены заполнителя во время выполнения. Затем вызовите `UpdateRegistryFromResourceD`, передавая массив для *pMapEntries* параметра. Это добавляет все значения замены `_ATL_REGMAP_ENTRIES` структур карту замены регистратора.  
  
> [!NOTE]
>  Статическое связывание компонент реестра ATL (регистратор), см. в разделе [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS  
 По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
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
 *lpszRes*  
 [in] Имя ресурса.  
  
 *nResID*  
 [in] Идентификатор ресурса.  
  
 *bЗарегистрируйтесь участия*  
 [in] Указывает, является ли файл скрипта ресурсов должен быть зарегистрирован.  
  
 *pMapEntries*  
 [in] Указатель на карте замены хранения значений, связанных с подстановочных параметров сценария. ATL автоматически использует `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. в разделе "Примечания" Дополнительные сведения. В противном случае используйте значение по умолчанию NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Аналогичную [UpdateRegistryFromResourceD](#updateregistryfromresourced) за исключением `UpdateRegistryFromResourceS` создает статическую ссылку компонент реестра ATL (регистратор).  
  
 `UpdateRegistryFromResourceS` будет вызываться автоматически при обработке объекта карты условии добавления `#define _ATL_STATIC_REGISTRY` ваш файл stdafx.h.  
  
> [!NOTE]
>  Чтобы заменить значения замены во время выполнения, не указывайте [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) макрос. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структуры, где каждая запись содержит переменной заполнитель в паре со значением для замены заполнителя во время выполнения. Затем вызовите `UpdateRegistryFromResourceS`, передавая массив для *pMapEntries* параметра. Это добавляет все значения замены `_ATL_REGMAP_ENTRIES` структур карту замены регистратора.  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
