---
title: Класс CAtlModuleT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1dd5bd4c7bc88d0a0acc8abc18b0d7b3462b7f52
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880850"
---
# <a name="catlmodulet-class"></a>Класс CAtlModuleT
Этот класс реализует модуль ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `CAtlModuleT`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|Инициализирует элемент данных, содержащий идентификатор GUID для текущего модуля.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|Добавляет в реестр exe-файла.|  
|[CAtlModuleT::RegisterServer](#registerserver)|Добавляет службу в реестр.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Удаляет exe-файла из реестра.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Удаляет службу из реестра.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Обновляет сведения о exe-файла в реестре.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlModuleT`, производный от [CAtlModule](../../atl/reference/catlmodule-class.md), реализует исполняемый файл (EXE) или модуля ATL службы (EXE). Исполняемый модуль — это локальный вне процесса сервер, а модуль службы — это приложение Windows, которое выполняется в фоновом режиме, при запуске Windows.  
  
 `CAtlModuleT` предоставляет поддержку для инициализации, регистрация и Отмена регистрации модуля.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT  
 Конструктор.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [CAtlModuleT::InitLibId](#initlibid).  
  
##  <a name="initlibid"></a>  CAtlModuleT::InitLibId  
 Инициализирует элемент данных, содержащий идентификатор GUID для текущего модуля.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывается конструктором [CAtlModuleT::CAtlModuleT](#catlmodulet).  
  
##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId  
 Добавляет в реестр exe-файла.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer  
 Добавляет службу в реестр.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bRegTypeLib*  
 Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 *pCLSID*  
 Указывает идентификатор CLSID объекта для регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет зарегистрировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId  
 Удаляет exe-файла из реестра.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer  
 Удаляет службу из реестра.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bUnRegTypeLib*  
 Значение TRUE, если библиотека типов также для отмены регистрации.  
  
 *pCLSID*  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в карте объектов будет отменена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId  
 Обновляет сведения о exe-файла в реестре.  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bЗарегистрируйтесь участия*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlModule](../../atl/reference/catlmodule-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Модульные классы](../../atl/atl-module-classes.md)
