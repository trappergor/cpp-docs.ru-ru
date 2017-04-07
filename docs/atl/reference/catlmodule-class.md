---
title: "Класс CAtlModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>Класс CAtlModule
Этот класс предоставляет методы, используемые несколько классов ATL модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Конструктор.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Переопределите этот метод, чтобы добавить параметры карта замены компонент реестра ATL (регистратор).|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Добавляет новую функцию, вызываемый при завершении работы модуля.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Возвращает указатель на интерфейс.|  
|[CAtlModule::GetLockCount](#getlockcount)|Возвращает число блокировок.|  
|[CAtlModule::Lock](#lock)|Увеличивает счетчик блокировок.|  
|[CAtlModule::Term](#term)|Освобождает все члены данных.|  
|[CAtlModule::Unlock](#unlock)|Уменьшает на единицу счетчик блокировок.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Этот метод вызывается методом `UpdateRegistryFromResourceD` для обновления реестра.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта. Компонент реестра ATL статически связывает этот метод.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Содержит идентификатор GUID текущего модуля.|  
|[CAtlModule::m_pGIT](#m_pgit)|Указатель на общую таблицу интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется [класса CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md), [класса CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), и [CAtlServiceModuleT класса](../../atl/reference/catlservicemodulet-class.md) для обеспечения поддержки приложений DLL, exe-приложения и службы Windows, соответственно.  
  
 Дополнительные сведения о модулях в ATL см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).  
  
 Этот класс заменяет устаревшие [CComModule-класс](../../atl/reference/ccommodule-class.md) использовался в предыдущих версиях библиотеки ATL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 Переопределите этот метод, чтобы добавить параметры карта замены компонент реестра ATL (регистратор).  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Параметры  
 *pRegistrar*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Подстановочные параметры позволяют клиенту регистратора для указания данных времени выполнения. Чтобы сделать это, регистратор поддерживает замены карты, в который он входит значения, связанные с подставляемые параметры в скрипте. Регистратор делает эти записи во время выполнения.  
  
 См. в разделе [с помощью подстановочных параметров (препроцессор регистратора)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) для получения дополнительных сведений.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 Добавляет новую функцию, вызываемый при завершении работы модуля.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pFunc*  
 Указатель на функцию для добавления.  
  
 `dw`  
 Определяемые пользователем данные, переданные в функцию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 Конструктор.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует элементы данных и инициирует критическую секцию вокруг поток модуля.  
  
##  <a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 Деструктор  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Извлекает указатель на глобальную таблицу интерфейса.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ppGIT`  
 Указатель на переменную, которая получит указатель на глобальную таблицу интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успеха или код ошибки в случае сбоя. Если возвращается E_POINTER `ppGIT` равен NULL.  
  
### <a name="remarks"></a>Примечания  
 Если объект глобальной таблицы интерфейсов не существует, он создается и его адрес хранится в переменной-члена [CAtlModule::m_pGIT](#m_pgit).  
  
 В отладочных построениях, произойдет ошибка утверждения, если `ppGIT` равен NULL, или если не удается получить указатель глобальной таблицы интерфейсов.  
  
 В разделе [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) сведения о глобальной таблицы интерфейсов.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 Возвращает число блокировок.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число блокировок. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 Увеличивает счетчик блокировок.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Увеличивает счетчик блокировок и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 Содержит идентификатор GUID текущего модуля.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 Указатель на общую таблицу интерфейса.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 Освобождает все члены данных.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все члены данных. Этот метод вызывается деструктором.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 Уменьшает на единицу счетчик блокировок.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уменьшает счетчик блокировок и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта.  
  
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
 Указатель на карту замены хранения значений, связанных с подставляемые параметры сценария. ATL автоматически использует модуль %. Для использования дополнительных подстановочных параметров см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае, используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Запускает скрипт, содержащийся в ресурс, указанный параметром *lpszRes или nResID*. Если `bRegister` — **TRUE**, этот метод регистрирует объект в системном реестре; в противном случае удаляет объект из реестра.  
  
 Статическое связывание компонент реестра ATL (регистратор), в разделе [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Этот метод вызывает метод [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) и [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
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
 Указатель на карту замены хранения значений, связанных с подставляемые параметры сценария. ATL автоматически использует модуль %. Для использования дополнительных подстановочных параметров см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае, используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод предоставляет реализацию [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 Запускает скрипт, содержащийся в указанный ресурс, чтобы зарегистрировать или отменить регистрацию объекта. Компонент реестра ATL статически связывает этот метод.  
  
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
 Указывает, зарегистрировано ли скрипт ресурсов.  
  
 `pMapEntries`  
 Указатель на карту замены хранения значений, связанных с подставляемые параметры сценария. ATL автоматически использует модуль %. Для использования дополнительных подстановочных параметров см. [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). В противном случае, используйте **NULL** значение по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Аналогично [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) за исключением `CAtlModule::UpdateRegistryFromResourceS` создает статический ссылку на компонент реестра ATL (регистратор).  
  
## <a name="see-also"></a>См. также  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)   
 [Компонент реестра (регистратор)](../../atl/atl-registry-component-registrar.md)  

