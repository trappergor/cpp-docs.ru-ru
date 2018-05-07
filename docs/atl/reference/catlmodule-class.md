---
title: Класс CAtlModule | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be5d5a777d4b9aed9ee4d07016771ee91c913b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="catlmodule-class"></a>Класс CAtlModule
Этот класс предоставляет методы, используемые несколькими модульные классы ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Конструктор.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Переопределите этот метод для добавления параметров к карте замены компонент реестра ATL (регистратор).|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Добавляет новую функцию, вызываемый при завершении модуля.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Возвращает указатель на интерфейс.|  
|[CAtlModule::GetLockCount](#getlockcount)|Возвращает число блокировок.|  
|[CAtlModule::Lock](#lock)|Увеличивает счетчик блокировок.|  
|[CAtlModule::Term](#term)|Освобождает все члены данных.|  
|[CAtlModule::Unlock](#unlock)|Уменьшает на единицу счетчик блокировок.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Этот метод вызывается методом `UpdateRegistryFromResourceD` для обновления реестра.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта. Компонент реестра ATL статически связывает этот метод.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Содержит идентификатор GUID для текущего модуля.|  
|[CAtlModule::m_pGIT](#m_pgit)|Указатель глобальной таблицы интерфейсов.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется [класса CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md), [класса CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), и [CAtlServiceModuleT класса](../../atl/reference/catlservicemodulet-class.md) для предоставления поддержки для приложения DLL, EXE-файла и Службы Windows, соответственно.  
  
 Дополнительные сведения о модулях в ATL см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).  
  
 Этот класс заменяет устаревшее [CComModule-класс](../../atl/reference/ccommodule-class.md) использовалась в предыдущих версиях библиотеки ATL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements  
 Переопределите этот метод для добавления параметров к карте замены компонент реестра ATL (регистратор).  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Параметры  
 *pRegistrar*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Подстановочные параметры позволяют клиенту регистратора указания данных во время выполнения. Чтобы сделать это, регистратор поддерживает замены карты, в которую он входит в значения, связанные с подстановочные параметры в скрипте. Регистратор делает эти записи во время выполнения.  
  
 См. в разделе [с помощью подстановочные параметры (препроцессор регистратора)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) для получения дополнительных сведений.  
  
##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc  
 Добавляет новую функцию, вызываемый при завершении модуля.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pFunc*  
 Указатель на функцию, чтобы добавить.  
  
 `dw`  
 Определяемые пользователем данные, передаваемые функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="catlmodule"></a>  CAtlModule::CAtlModule  
 Конструктор.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует данные-члены и инициирует критическую секцию вокруг поток модуля.  
  
##  <a name="dtor"></a>  CAtlModule:: ~ CAtlModule  
 Деструктор  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных.  
  
##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr  
 Извлекает указатель на общая таблица интерфейса.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ppGIT`  
 Указатель на переменную, которая получит указатель общая таблица интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, в случае успеха или код ошибки при неудаче. Если возвращается E_POINTER `ppGIT` равен NULL.  
  
### <a name="remarks"></a>Примечания  
 Если общая таблица интерфейса объект не существует, он создается и его адрес хранится в переменной-члена [CAtlModule::m_pGIT](#m_pgit).  
  
 В отладочных построениях, произойдет ошибка утверждения, если `ppGIT` равен NULL, или если не удается получить указатель глобальной таблицы интерфейсов.  
  
 В разделе [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) сведения о общая таблица интерфейса.  
  
##  <a name="getlockcount"></a>  CAtlModule::GetLockCount  
 Возвращает число блокировок.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число блокировок. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="lock"></a>  CAtlModule::Lock  
 Увеличивает счетчик блокировок.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Увеличивает счетчик блокировок и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="m_libid"></a>  CAtlModule::m_libid  
 Содержит идентификатор GUID для текущего модуля.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>  CAtlModule::m_pGIT  
 Указатель глобальной таблицы интерфейсов.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>  CAtlModule::Term  
 Освобождает все члены данных.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных. Этот метод вызывается деструктором.  
  
##  <a name="unlock"></a>  CAtlModule::Unlock  
 Уменьшает на единицу счетчик блокировок.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уменьшает счетчик блокировок и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="updateregistryfromresourced"></a>  CAtlModule::UpdateRegistryFromResourceD  
 Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszRes`  
 Имя ресурса.  
  
 `nResID`  
 Идентификатор ресурса.  
  
 `bRegister`  
 **Значение TRUE,** , если объект должен быть зарегистрирован; **FALSE** в противном случае.  
  
 `pMapEntries`  
 Указатель на карту замены хранения значений, связанных с подстановочные параметры этого сценария. ATL автоматически использует модуль %. Чтобы использовать дополнительные подстановочные параметры, см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Запускает скрипт, содержащийся в ресурс, указанный параметром *lpszRes или nResID*. Если `bRegister` — **TRUE**, этот метод регистрирует объект в системном реестре; в противном случае удаляет объект из реестра.  
  
 Статическое связывание компонент реестра ATL (регистратор), в разделе [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Этот метод вызывает метод [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) и [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper  
 Этот метод вызывается методом `UpdateRegistryFromResourceD` для обновления реестра.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszRes`  
 Имя ресурса.  
  
 `bRegister`  
 Указывает, зарегистрировано ли объект.  
  
 `pMapEntries`  
 Указатель на карту замены хранения значений, связанных с подстановочные параметры этого сценария. ATL автоматически использует модуль %. Чтобы использовать дополнительные подстановочные параметры, см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод предоставляет реализацию [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>  CAtlModule::UpdateRegistryFromResourceS  
 Выполняет скрипт, содержащийся в указанный ресурс для регистрации или отмены регистрации объекта. Компонент реестра ATL статически связывает этот метод.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nResID`  
 Идентификатор ресурса.  
  
 `lpszRes`  
 Имя ресурса.  
  
 `bRegister`  
 Указывает, зарегистрировано ли файл скрипта ресурсов.  
  
 `pMapEntries`  
 Указатель на карту замены хранения значений, связанных с подстановочные параметры этого сценария. ATL автоматически использует модуль %. Чтобы использовать дополнительные подстановочные параметры, см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) за исключением `CAtlModule::UpdateRegistryFromResourceS` создает статическую ссылку на компонент реестра ATL (регистратор).  
  
## <a name="see-also"></a>См. также  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)   
 [Компонент реестра (регистратор)](../../atl/atl-registry-component-registrar.md)  
