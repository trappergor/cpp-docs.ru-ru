---
title: "CComModule-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d2bd7566a25cd135cb541c4d90f2700b5f0d47b2
ms.lasthandoff: 02/24/2017

---
# <a name="ccommodule-class"></a>CComModule-класс
Начиная с ATL 7.0 `CComModule` является устаревшим: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Создает объект для указанного идентификатора CLSID. Для DLL.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Возвращает `m_hInst`.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Возвращает `m_hInstResource`.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Возвращает `m_hInstTypeLib`.|  
|[CComModule::Init](#init)|Инициализирует элементы данных.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Регистрация стандартного класса объекта переходит в системном реестре.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса. EXE-файлами только.|  
|[CComModule::RegisterServer](#registerserver)|Обновление системного реестра для каждого объекта в схеме объекта.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Регистрирует библиотеку типов.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса. EXE-файлами только.|  
|[CComModule::Term](#term)|Освобождает членов данных.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Удаляет регистрацию стандартный класс объекта из системного реестра.|  
|[CComModule::UnregisterServer](#unregisterserver)|Отменяет регистрацию каждого объекта в схеме объекта.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Регистрирует или отменяет регистрацию стандартный класс объекта.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Статически ссылки на компонент реестра ATL. Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Обеспечивает синхронизированный доступ к информации карты объекта.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Обеспечивает синхронизированного доступа к информации о библиотеке типов.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Обеспечивает синхронизированного доступа к информации в окне классов и статических данных, используемых во время создания окна.|  
|[CComModule::m_hInst](#m_hinst)|Содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstResource](#m_hinstresource)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|По умолчанию содержит дескриптор экземпляра модуля.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Указывает объект карты, поддерживаемый экземпляр модуля.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот класс является устаревшим, и теперь использование мастеров создания кода ATL [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) и [CAtlModule](../../atl/reference/catlmodule-class.md) производных классов. В разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее. Приведенные далее сведения предназначено для использования с приложениями, созданными с помощью более старые версии библиотеки ATL. `CComModule`по-прежнему частью библиотеки ATL обратной возможностей.  
  
 `CComModule`реализует модуль сервера COM, что позволяет клиенту получить доступ к компонентам модуля. `CComModule`поддерживает библиотеки DLL (в процессе) и exe-ФАЙЛ (локальные) модули.  
  
 A `CComModule` экземпляр использует схему объекта для поддержания набор определений объектов. Этот объект карты реализуется как массив `_ATL_OBJMAP_ENTRY` структур и содержит сведения о:  
  
-   Ввод и удаление описания объектов в системном реестре.  
  
-   Создание экземпляров объектов с помощью фабрики класса.  
  
-   Установление связи между клиентом и корневой объект в компоненте.  
  
-   Выполнение управления временем существования объектов классов.  
  
 Когда вы запускаете мастер приложений COM ATL, мастер автоматически создает `_Module`, глобальный экземпляр класса `CComModule` или класс, производный от него. Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
 В дополнение к `CComModule`, библиотека ATL предоставляет [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), который реализует модуль модели подразделения для EXE-файлов и служб Windows. Наследовать от вашего модуля `CComAutoThreadModule` используется для создания объектов в нескольких подразделениях.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Требования  
 `Header:`atlbase.h  
  
##  <a name="a-namegetclassobjecta--ccommodulegetclassobject"></a><a name="getclassobject"></a>CComModule::GetClassObject  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [out] Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppv` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.  
  
 `GetClassObject`доступен только для библиотеки DLL.  
  
##  <a name="a-namegetmoduleinstancea--ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Определение этого модуля.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInst](#m_hinst) данные-член.  
  
##  <a name="a-namegetresourceinstancea--ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HINSTANCE`.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstResource](#m_hinstresource) данные-член.  
  
##  <a name="a-namegettypelibinstancea--ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `HINSTANCE`.  
  
### <a name="remarks"></a>Примечания  
 Возвращает [m_hInstTypeLib](#m_hinsttypelib) данные-член.  
  
##  <a name="a-nameinita--ccommoduleinit"></a><a name="init"></a>CComModule::Init  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [in] `HINSTANCE` Переданы **DLLMain** или `WinMain`.  
  
 `plibid`  
 [in] Указатель на идентификатор LIBID библиотеки типов, связанных с проектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует все члены данных.  
  
##  <a name="a-namemcsobjmapa--ccommodulemcsobjmap"></a><a name="m_csobjmap"></a>CComModule::m_csObjMap  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к схеме объекта.  
  
##  <a name="a-namemcstypeinfoholdera--ccommodulemcstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к библиотеке типов.  
  
##  <a name="a-namemcswindowcreatea--ccommodulemcswindowcreate"></a><a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Примечания  
 Обеспечивает синхронизированного доступа к информации о класс окна и статические данные, используемые при создании окна.  
  
##  <a name="a-namemhinsta--ccommodulemhinst"></a><a name="m_hinst"></a>CComModule::m_hInst  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Примечания  
 Содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInst` в дескриптор, переданный **DLLMain** или `WinMain`.  
  
##  <a name="a-namemhinstresourcea--ccommodulemhinstresource"></a><a name="m_hinstresource"></a>CComModule::m_hInstResource  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstResource` в дескриптор, переданный **DLLMain** или `WinMain`. Можно явно задать `m_hInstResource` дескриптор ресурса.  
  
 [GetResourceInstance](#getresourceinstance) метод возвращает дескриптор, хранящиеся в `m_hInstResource`.  
  
##  <a name="a-namemhinsttypeliba--ccommodulemhinsttypelib"></a><a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию содержит дескриптор экземпляра модуля.  
  
 [Init](#init) метода задает `m_hInstTypeLib` в дескриптор, переданный **DLLMain** или `WinMain`. Можно явно задать `m_hInstTypeLib` дескриптора в библиотеку типов.  
  
 [GetTypeLibInstance](#gettypelibinstance) метод возвращает дескриптор, хранящиеся в `m_hInstTypeLib`.  
  
##  <a name="a-namempobjmapa--ccommodulempobjmap"></a><a name="m_pobjmap"></a>CComModule::m_pObjMap  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Примечания  
 Указывает объект карты, поддерживаемый экземпляр модуля.  
  
##  <a name="a-nameregisterclasshelpera--ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [in] Независимый от версии идентификатор ProgID связанный с объектом.  
  
 `nDescID`  
 [in] Идентификатор строкового ресурса для описания объекта.  
  
 `dwFlags`  
 [in] Указывает потоковую модель, чтобы ввести в реестре. Возможные значения: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Регистрация стандартного класса объекта переходит в системном реестре.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы метода `RegisterClassHelper`.  
  
##  <a name="a-nameregisterclassobjectsa--ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwClsContext`  
 [in] Указывает контекст, в котором будет выполняться объекта класса. Возможные значения: **CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, или **CLSCTX_LOCAL_SERVER**. Описание этих значений см. в разделе [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwFlags`  
 [in] Определяет типы подключения к объекту класса. Возможные значения: **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, или **REGCLS_MULTI_SEPARATE**. Описание этих значений см. в разделе [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Регистрирует объект класса EXE OLE другим приложениям подключаться к нему. Этот метод доступен только для EXE-файлов.  
  
##  <a name="a-nameregisterservera--ccommoduleregisterserver"></a><a name="registerserver"></a>CComModule::RegisterServer  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 [in] Указывает, будет ли зарегистрирована библиотека типов. Значение по умолчанию — **FALSE**.  
  
 `pCLSID`  
 [in] Указывает на идентификатор CLSID регистрируемого объекта. Если **NULL** (значение по умолчанию), будет регистрироваться все объекты в схеме объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от `pCLSID` параметра обновляет системный реестр для одного класса объекта или для всех объектов в карте объектов.  
  
 Если `bRegTypeLib` — **TRUE**, также будут обновлены сведения о библиотеке типов.  
  
 В разделе [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) сведения о том, как добавить запись в карте объектов.  
  
 `RegisterServer`будет вызываться автоматически **DLLRegisterServer** для библиотеки DLL или с помощью `WinMain` для запуска с помощью EXE-файла **/regserver** параметр командной строки.  
  
##  <a name="a-nameregistertypeliba--ccommoduleregistertypelib"></a><a name="registertypelib"></a>CComModule::RegisterTypeLib  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 [in] Строка в формате `"\\N"`, где `N` имеет целочисленный индекс ресурса библиотеки ТИПОВ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Добавляет сведения о библиотеке типов в системный реестр.  
  
 Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов можно использовать второй версии этого метода.  
  
##  <a name="a-namerevokeclassobjectsa--ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет объект класса. Этот метод доступен только для EXE-файлов.  
  
##  <a name="a-nameterma--ccommoduleterm"></a><a name="term"></a>CComModule::Term  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных.  
  
##  <a name="a-nameunregisterclasshelpera--ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [in] Независимый от версии идентификатор ProgID связанный с объектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Удаляет регистрацию стандартный класс объекта из системного реестра.  
  
 [UpdateRegistryClass](#updateregistryclass) вызовы метода `UnregisterClassHelper`.  
  
##  <a name="a-nameunregisterservera--ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::UnregisterServer  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
  
 `UnregisterServer`будет вызываться автоматически **DLLUnregisterServer** для библиотеки DLL или с помощью `WinMain` для запуска с помощью EXE-файла **/UnregServer** параметр командной строки.  
  
 В разделе [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) сведения о том, как добавить запись в карте объектов.  
  
##  <a name="a-nameupdateregistryclassa--ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 Идентификатор CLSID объекта, для регистрации или отмены регистрации.  
  
 `lpszProgID`  
 Идентификатор ProgID, связанный с объектом.  
  
 `lpszVerIndProgID`  
 Независимый от версии идентификатор ProgID связанный с объектом.  
  
 `nDescID`  
 Идентификатор строкового ресурса для описания объекта.  
  
 `szDesc`  
 Строка, содержащая описание объекта.  
  
 `dwFlags`  
 Указывает потоковую модель, чтобы ввести в реестре. Возможные значения: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
 `bRegister`  
 Указывает, зарегистрировано ли объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если `bRegister` — **TRUE**, этот метод вводит регистрации стандартный класс объекта в системном реестре.  
  
 Если `bRegister` — **FALSE**, он удаляет регистрацию объекта.  
  
 В зависимости от значения `bRegister`, `UpdateRegistryClass` вызывает либо [RegisterClassHelper](#registerclasshelper) или [UnregisterClassHelper](#unregisterclasshelper).  
  
 Указав [DECLARE_REGISTRY](http://msdn.microsoft.com/library/89b8949b-5c27-4a9c-8a51-ad276bba3a54) макрос, `UpdateRegistryClass` запускается автоматически при обработке объекта карты.  
  
##  <a name="a-nameupdateregistryfromresourceda--ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [in] Указатель на карту замены хранения значений, связанных с подставляемые параметры сценария. ATL автоматически использует `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. заметки подробные сведения. В противном случае, используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Запускает скрипт, содержащийся в ресурс, указанный параметром `lpszRes` или `nResID`.  
  
 Если `bRegister` — **TRUE**, этот метод регистрирует объект в системном реестре; в противном случае — отменяет регистрацию объекта.  
  
 Указав [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) или [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) макрос, `UpdateRegistryFromResourceD` запускается автоматически при обработке объекта карты.  
  
> [!NOTE]
>  Чтобы заменить замены значения во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** структуры, где каждая запись содержит переменную заполнитель в паре со значением, замените заполнитель во время выполнения. Затем вызовите `UpdateRegistryFromResourceD`, передав массив для `pMapEntries` параметр. Это добавляет все значения замены **_ATL_REGMAP_ENTRIES** структуры карты замены регистратора.  
  
> [!NOTE]
>  Статическое связывание компонент реестра ATL (регистратор), в разделе [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="a-nameupdateregistryfromresourcesa--ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 Начиная с ATL 7.0 `CComModule` устарел: в разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
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
 [in] Указывает, зарегистрировано ли скрипт ресурсов.  
  
 `pMapEntries`  
 [in] Указатель на карту замены хранения значений, связанных с подставляемые параметры сценария. ATL автоматически использует `%MODULE%`. Чтобы использовать дополнительные подстановочные параметры, см. заметки подробные сведения. В противном случае, используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [UpdateRegistryFromResourceD](#updateregistryfromresourced) за исключением `UpdateRegistryFromResourceS` создает статический ссылку на компонент реестра ATL (регистратор).  
  
 `UpdateRegistryFromResourceS`запускается автоматически при обработке объекта карты условии добавления `#define _ATL_STATIC_REGISTRY` ваш файл stdafx.h.  
  
> [!NOTE]
>  Чтобы заменить замены значения во время выполнения, не указывайте [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) или [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** структуры, где каждая запись содержит переменную заполнитель в паре со значением, замените заполнитель во время выполнения. Затем вызовите `UpdateRegistryFromResourceS`, передав массив для `pMapEntries` параметр. Это добавляет все значения замены **_ATL_REGMAP_ENTRIES** структуры карты замены регистратора.  
  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

