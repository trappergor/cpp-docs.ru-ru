---
title: "Класс CAtlModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
dev_langs:
- C++
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9c0c6a2302932df06db7166d83fe9a561dfe38ac
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodulet-class"></a>Класс CAtlModuleT
Этот класс реализует ATL модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Ваш класс, производный от `CAtlModuleT`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|Инициализирует элемент данных, содержащая GUID текущего модуля.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|Exe-ФАЙЛ, добавляет в реестр.|  
|[CAtlModuleT::RegisterServer](#registerserver)|Добавляет службу в реестре.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Удаление exe-файла из реестра.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Удаляет службу из реестра.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Обновляет сведения о exe-файла в реестре.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlModuleT`, производный от [CAtlModule](../../atl/reference/catlmodule-class.md), реализующий исполняемый файл (EXE) или модуль ATL службы (EXE). Исполняемый модуль является сервером локального, out of process, тогда как модуль службы представляет собой приложение Windows, который выполняется в фоновом режиме при запуске Windows.  
  
 `CAtlModuleT`обеспечивает поддержку для инициализации, регистрация и Отмена регистрации модуля.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT  
 Конструктор.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlModuleT::InitLibId](#initlibid).  
  
##  <a name="initlibid"></a>CAtlModuleT::InitLibId  
 Инициализирует элемент данных, содержащая GUID текущего модуля.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывается конструктор [CAtlModuleT::CAtlModuleT](#catlmodulet).  
  
##  <a name="registerappid"></a>CAtlModuleT::RegisterAppId  
 Exe-ФАЙЛ, добавляет в реестр.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="registerserver"></a>CAtlModuleT::RegisterServer  
 Добавляет службу в реестре.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 `pCLSID`  
 Указывает на идентификатор CLSID регистрируемого объекта. Если значение NULL (значение по умолчанию), все объекты в схеме объекта будет зарегистрирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId  
 Удаление exe-файла из реестра.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="unregisterserver"></a>CAtlModuleT::UnregisterServer  
 Удаляет службу из реестра.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bUnRegTypeLib`  
 Значение TRUE, если библиотека типов также должна быть отменена.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в схеме объекта, будут удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
##  <a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId  
 Обновляет сведения о exe-файла в реестре.  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bRegister`  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlModule](../../atl/reference/catlmodule-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)

