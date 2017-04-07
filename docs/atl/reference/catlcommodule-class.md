---
title: "Класс CAtlComModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 6b933b5388fccc2dc0e31d035aa7eb56de3b1866
ms.lasthandoff: 02/24/2017

---
# <a name="catlcommodule-class"></a>Класс CAtlComModule
Этот класс реализует COM серверный модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|Конструктор.|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|Этот метод вызывается для обновления системного реестра для каждого объекта в схеме объекта.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Этот метод вызывается для регистрации библиотеки типов.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|Этот метод вызывается для отмены регистрации каждого объекта в схеме объекта.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Этот метод вызывается для отмены регистрации библиотеки типов.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlComModule`реализует модуль сервера COM, что позволяет клиенту получить доступ к компонентам модуля.  
  
 Этот класс заменяет устаревшие [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в предыдущих версиях библиотеки ATL. В разделе [модульные классы ATL](../../atl/atl-module-classes.md) подробнее.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="catlcommodule"></a>CAtlComModule::CAtlComModule  
 Конструктор.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует модуль.  
  
##  <a name="dtor"></a>CAtlComModule:: ~ CAtlComModule  
 Деструктор  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все фабрики класса.  
  
##  <a name="registerserver"></a>CAtlComModule::RegisterServer  
 Этот метод вызывается для обновления системного реестра для каждого объекта в схеме объекта.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 `pCLSID`  
 Указывает на идентификатор CLSID регистрируемого объекта. Если значение NULL (значение по умолчанию), все объекты в схеме объекта будет зарегистрирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию глобального [AtlComModuleRegisterServer](http://msdn.microsoft.com/library/d11a0c91-0c56-4b1b-a5f5-1287970f798b).  
  
##  <a name="registertypelib"></a>CAtlComModule::RegisterTypeLib  
 Этот метод вызывается для регистрации библиотеки типов.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса библиотеки ТИПОВ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Добавляет сведения о библиотеке типов в системный реестр. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов следует использовать первой версии этого метода.  
  
##  <a name="unregisterserver"></a>CAtlComModule::UnregisterServer  
 Этот метод вызывается для отмены регистрации каждого объекта в схеме объекта.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegTypeLib`  
 Значение TRUE, если для отмены регистрации библиотеки типов. Значение по умолчанию — FALSE.  
  
 `pCLSID`  
 Указывает идентификатор CLSID объекта для отмены регистрации. Если значение NULL (значение по умолчанию), все объекты в схеме объекта, будут удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Вызывает функцию глобального [AtlComModuleUnregisterServer](http://msdn.microsoft.com/library/c4ef3da4-def7-4aaf-b005-573a02e389d5).  
  
##  <a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib  
 Этот метод вызывается для отмены регистрации библиотеки типов.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 Строка в формате «\\\N», где N — целочисленный индекс ресурса библиотеки ТИПОВ.  
  
### <a name="remarks"></a>Примечания  
 Удаляет сведения о библиотеке типов из системного реестра. Если экземпляр модуля содержит несколько библиотек типов, позволяет указать, какие библиотеки типов следует использовать первой версии этого метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

