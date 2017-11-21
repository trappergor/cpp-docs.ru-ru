---
title: "Глобальные функции регистрации сервера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs: C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 300cab10480adf201bf6bf0b0275bb0f331c2602
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="server-registration-global-functions"></a>Глобальные функции для регистрации сервера
Эти функции обеспечивают поддержку для регистрации и отмены регистрации серверных объектов в карте объектов.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Эта функция вызывается для регистрации каждого из объектов в карте объектов.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Эта функция вызывается для регистрации объектов класса.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Эта функция вызывается для отмены объектов классов из COM-модуля.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Эта функция вызывается для получения объекта класса.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
 Эта функция вызывается для регистрации каждого из объектов в карте объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на COM-модуля.  
  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов.  
  
 `pCLSID`  
 Указывает идентификатор CLSID регистрируемого объекта. Если значение равно NULL, будет зарегистрирована всех объектов в карте объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 `AtlComModuleRegisterServer`проходит по карте объектов ATL автоматически формируемые и регистрирует каждый объект в карте. Если `pCLSID` не является NULL, то только объект, на который ссылается `pCLSID` зарегистрирован; в противном случае все объекты зарегистрированы.  
  
 Эта функция вызывается [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
 Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на COM-модуля.  
  
 `bUnRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение равно NULL всех объектов в карте объектов будет отменена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 `AtlComModuleUnregisterServer`проходит по схеме объекта ATL и отменяет регистрацию каждого объекта в схеме. Если `pCLSID` не является NULL, то только объект, на который ссылается `pCLSID` отменена; в противном случае все объекты, не зарегистрированы.  
  
 Эта функция вызывается [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
 Эта функция вызывается для регистрации объектов класса.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на COM-модуля.  
  
 `dwClsContext`  
 Указывает контекст, в котором будет выполняться объекта класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. В разделе [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) для получения дополнительных сведений.  
  
 `dwFlags`  
 Определяет типы подключения к такому объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. В разделе [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 Эта функция вызывается для удаления фабрики или фабрик класса из таблицы запущенных объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на COM-модуля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
 Эта функция вызывается для получения фабрики класса.  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на COM-модуля.  
  
 `rclsid`  
 CLSID объекта должен быть создан.  
  
 `riid`  
 Идентификатор IID запрошенного интерфейса.  
  
 `ppv`  
 Указатель на указатель на интерфейс, определяемый `riid`. Если объект не поддерживает этот интерфейс `ppv` имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (устаревший в ATL 7.0) и [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
