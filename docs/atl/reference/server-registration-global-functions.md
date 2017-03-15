---
title: "Глобальные функции регистрации сервера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
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
ms.openlocfilehash: 4ace3bb50d824827071260e3f43cec3cda32742f
ms.lasthandoff: 02/24/2017

---
# <a name="server-registration-global-functions"></a>Глобальные функции регистрации сервера
Эти функции обеспечивают поддержку для регистрации и отмены регистрации серверных объектов в карте объектов.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Эта функция вызывается для регистрации каждого из объектов в карте объектов.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Эта функция вызывается для регистрации объектов класса.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Эта функция вызывается для отмены объекты классов из COM-модуле.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Эта функция вызывается для получения объекта класса.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="a-nameatlcommoduleregisterservera--atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
 Эта функция вызывается для регистрации каждого из объектов в карте объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на модуль COM.  
  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов.  
  
 `pCLSID`  
 Указывает на идентификатор CLSID регистрируемого объекта. Если значение равно NULL, будут зарегистрированы все объекты в схеме объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `AtlComModuleRegisterServer`проходит карты автоматически созданный объект ATL и регистрирует каждый объект в сопоставлении. Если `pCLSID` не NULL, то только объект, на который ссылается `pCLSID` зарегистрирован; в противном случае регистрируются все объекты.  
  
 Эта функция вызывается [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="a-nameatlcommoduleunregisterservera--atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
 Эта функция вызывается для отмены регистрации каждого из объектов в карте объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на модуль COM.  
  
 `bUnRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение равно NULL будет отменить регистрацию всех объектов в карте объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `AtlComModuleUnregisterServer`проходит по схеме объекта ATL и отменяет регистрацию каждого объекта в схеме. Если `pCLSID` не NULL, то только объект, на который ссылается `pCLSID` отменена; в противном случае все объекты, не зарегистрированы.  
  
 Эта функция вызывается [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="a-nameatlcommoduleregisterclassobjectsa--atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
 Эта функция вызывается для регистрации объектов класса.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на модуль COM.  
  
 `dwClsContext`  
 Указывает контекст, в котором будет выполняться объекта класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER. В разделе [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) для получения дополнительных сведений.  
  
 `dwFlags`  
 Определяет типы подключения к объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE. В разделе [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="a-nameatlcommodulerevokeclassobjectsa--atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 Эта функция вызывается для удаления фабрики или фабрик класса из таблицы запущенных объектов.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Параметры  
 `pComModule`  
 Указатель на модуль COM.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (устаревший в ATL 7.0) и [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="a-nameatlcommodulegetclassobjecta--atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
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
 Указатель на модуль COM.  
  
 `rclsid`  
 CLSID объекта должен быть создан.  
  
 `riid`  
 Идентификатор IID запрошенного интерфейса.  
  
 `ppv`  
 Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppv` имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта вспомогательная функция используемой [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (устаревший в ATL 7.0) и [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

