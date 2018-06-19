---
title: Класс CAtlBaseModule | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07f1252fe993ff2f2e646528996c1a53d25c5a63
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360323"
---
# <a name="catlbasemodule-class"></a>Класс CAtlBaseModule
В каждом проекте ATL создается экземпляр этого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Добавляет в список хранимых дескрипторов экземпляра ресурса.|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Возвращает дескриптор для указанного экземпляра ресурса.|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Возвращает экземпляр модуля из `CAtlBaseModule` объекта.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Возвращает экземпляр ресурса из `CAtlBaseModule` объекта.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Удаляет экземпляр ресурса из списка хранимых дескрипторов.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Задает экземпляр ресурса `CAtlBaseModule` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Переменная, которая указывает на сбой при инициализации модуля.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `CAtlBaseModule` именованный _AtlBaseModule присутствует в каждом проекте ATL, содержащая дескриптор экземпляра модуля, дескриптор модуля, содержащего ресурсы (которые по умолчанию находятся в одной и той же) и массив дескрипторов для модулей, предоставляя основной ресурсы. `CAtlBaseModule` безопасного доступа из нескольких потоков.  
  
 Этот класс заменяет устаревшее [CComModule](../../atl/reference/ccommodule-class.md) класс, используемый в предыдущих версиях библиотеки ATL.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance  
 Добавляет в список хранимых дескрипторов экземпляра ресурса.  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInst`  
 Добавление экземпляра ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ресурс успешно добавляемых false в противном случае.  
  
##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule  
 Конструктор.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Создает объект `CAtlBaseModule`.  
  
##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt  
 Возвращает дескриптор для указанного экземпляра ресурса.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *i*  
 Номер экземпляра ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор экземпляра ресурса, или значение NULL, если существует без соответствующего экземпляра ресурса.  
  
##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance  
 Возвращает экземпляр модуля из `CAtlBaseModule` объекта.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экземпляр модуля.  
  
##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance  
 Возвращает экземпляр ресурса.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экземпляр ресурса.  
  
##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed  
 Переменная, которая указывает на сбой при инициализации модуля.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Примечания  
 Значение true, если модуль инициализирован, false, если не удалось выполнить инициализацию.  
  
##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance  
 Удаляет экземпляр ресурса из списка хранимых дескрипторов.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInst`  
 Для удаления экземпляра ресурса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ресурс успешно удален, и false в противном случае.  
  
##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance  
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
