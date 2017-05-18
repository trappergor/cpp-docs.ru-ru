---
title: "Класс CAtlBaseModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4897f6cf7e12a18401720ad663c90491bb0e599d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="catlbasemodule-class"></a>Класс CAtlBaseModule
В каждом проекте ATL создается экземпляр этого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Добавляет экземпляр ресурса в список хранимых дескрипторов.|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Возвращает дескриптор экземпляра указанного ресурса.|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Возвращает экземпляр модуля из `CAtlBaseModule` объекта.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Возвращает экземпляр ресурса из `CAtlBaseModule` объекта.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Удаляет экземпляр ресурса из списка хранимых маркеров.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Задает экземпляр ресурса `CAtlBaseModule` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Переменная, которая указывает на сбой при инициализации модуля.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `CAtlBaseModule` именованных _AtlBaseModule присутствует в каждом проекте ATL, содержащая дескриптор экземпляра модуля, дескриптор модуля, содержащего ресурсы (которые по умолчанию одно и то же) и массив дескрипторов к модулям, предоставляя основные ресурсы. `CAtlBaseModule`можно безопасно обращаться из нескольких потоков.  
  
 Этот класс заменяет устаревшие [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в предыдущих версиях библиотеки ATL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance  
 Добавляет экземпляр ресурса в список хранимых дескрипторов.  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInst`  
 Чтобы добавить экземпляр ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ресурс был успешно добавлен значение, false в противном случае.  
  
##  <a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule  
 Конструктор.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Создает объект `CAtlBaseModule`.  
  
##  <a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt  
 Возвращает дескриптор экземпляра указанного ресурса.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *i*  
 Номер экземпляра ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор экземпляра ресурса, или значение NULL, если отсутствует соответствующий экземпляр ресурса.  
  
##  <a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance  
 Возвращает экземпляр модуля из `CAtlBaseModule` объекта.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экземпляр модуля.  
  
##  <a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance  
 Возвращает экземпляр ресурса.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экземпляр ресурса.  
  
##  <a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed  
 Переменная, которая указывает на сбой при инициализации модуля.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Примечания  
 Значение true, если модуль инициализирован, false, если не удалось выполнить инициализацию.  
  
##  <a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance  
 Удаляет экземпляр ресурса из списка хранимых маркеров.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInst`  
 Чтобы удалить экземпляр ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ресурс успешно удален, и false в противном случае.  
  
##  <a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance  
 Задает экземпляр ресурса `CAtlBaseModule` объекта.  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInst`  
 Новый экземпляр ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экземпляр обновленный ресурс.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)

