---
title: Класс CAtlComModule | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47e85f3aab75f8fafb76977847ce36d37808af60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="catlcommodule-class"></a>Класс CAtlComModule
Этот класс реализует COM-модуля сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|Конструктор.|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|Этот метод используется для обновления системного реестра для каждого объекта в карте объектов.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Этот метод вызывается для регистрации библиотеки типов.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|Этот метод вызывается для отмены регистрации каждого из объектов в карте объектов.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Этот метод вызывается для отмены регистрации библиотеки типов.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlComModule` реализует COM-модуля сервера, что позволяет клиенту получить доступ к компонентам модуля.  
  
 Этот класс заменяет устаревшее [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в предыдущих версиях библиотеки ATL. В разделе [модульные классы ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule  
 Конструктор.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует модуль.  
  
##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule  
 Деструктор  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает всех фабрик классов.  
  
##  <a name="registerserver"></a>  CAtlComModule::RegisterServer  
 Этот метод используется для обновления системного реестра для каждого объекта в карте объектов.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 `pCLSID`  
 Указывает идентификатор CLSID регистрируемого объекта. Если значение NULL (значение по умолчанию), все объекты в схеме объекта будет зарегистрирована.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию глобального [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).  
  
##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib  
 Этот метод вызывается для регистрации библиотеки типов.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса TYPELIB.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Добавляет сведения о библиотеке типов в системный реестр. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов следует использовать первая версия этого метода.  
  
##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer  
 Этот метод вызывается для отмены регистрации каждого из объектов в карте объектов.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для отмены регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в схеме объекта будет отменена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию глобального [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).  
  
##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib  
 Этот метод вызывается для отмены регистрации библиотеки типов.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса TYPELIB.  
  
### <a name="remarks"></a>Примечания  
 Удаляет сведения о библиотеке типов из системного реестра. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов следует использовать первая версия этого метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
## <a name="see-also"></a>См. также  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
