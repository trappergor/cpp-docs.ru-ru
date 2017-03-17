---
title: "Класс CAtlDllModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13cd0adb860660e06c92e8f02c07721ede391fb7
ms.lasthandoff: 02/24/2017

---
# <a name="catldllmodulet-class"></a>Класс CAtlDllModuleT
Этот класс представляет модуль для библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Ваш класс, производный от `CAtlDllModuleT`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Конструктор.|  
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Проверяет DLL может быть выгружена.|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Возвращает фабрику классов.|  
|[CAtlDllModuleT::DllMain](#dllmain)|Точка входа необязательно в библиотеку динамической компоновки (DLL).|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Добавляет записи в системный реестр для объектов в библиотеке DLL.|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Удаляет записи в системном реестре для объектов в библиотеке DLL.|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Возвращает фабрику классов. Вызываемый по [DllGetClassObject](#dllgetclassobject).|  
  
## <a name="remarks"></a>Примечания  
 `CAtlDllModuleT`Представляет модуль для библиотеки динамической компоновки (DLL) и предоставляет функции, которые используются всеми проектами библиотеки DLL. Это специализация [CAtlModuleT](../../atl/reference/catlmodulet-class.md) класс включает в себя поддержку для регистрации.  
  
 Дополнительные сведения о модулях в ATL см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT  
 Конструктор.  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT  
 Деструктор  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow  
 Проверяет DLL может быть выгружена.  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если библиотека DLL может быть выгружен или S_FALSE, если это невозможно.  
  
##  <a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject  
 Возвращает фабрику классов.  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rclsid`  
 CLSID объекта должен быть создан.  
  
 `riid`  
 Идентификатор IID запрошенного интерфейса.  
  
 `ppv`  
 Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppv` имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 Точка входа необязательно в библиотеку динамической компоновки (DLL).  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwReason`  
 Если набор вызовов уведомления DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH и DLL_THREAD_DETACH отключены.  
  
 *lpReserved*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 Отключение DLL_THREAD_ATTACH и DLL_THREAD_DETACH вызовы уведомлений может быть полезным оптимизации для многопоточных приложений, имеющих многие библиотеки DLL, часто создания и удаления потоков и эти уведомления уровня потока вложения или отсоединение не обязательно, для библиотек DLL.  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 Добавляет записи в системный реестр для объектов в библиотеке DLL.  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 Удаляет записи в системном реестре для объектов в библиотеке DLL.  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bUnRegTypeLib`  
 Значение TRUE, если библиотека типов удаляются из реестра. Значение по умолчанию — TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="getclassobject"></a>CAtlDllModuleT::GetClassObject  
 Создает объект для указанного идентификатора CLSID.  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rclsid`  
 CLSID объекта должен быть создан.  
  
 `riid`  
 Идентификатор IID запрошенного интерфейса.  
  
 `ppv`  
 Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppv` имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) и включена для обратной совместимости.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)   
 [Класс CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)

