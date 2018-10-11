---
title: Класс IAccessorImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5de49679652b04afa4df08ce9d4ea015ebd031d
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082727"
---
# <a name="iaccessorimpl-class"></a>Класс IAccessorImpl

Предоставляет реализацию [IAccessor](/previous-versions/windows/desktop/ms719672) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, 
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
### <a name="parameters"></a>Параметры  

*T*<br/>
Класс объекта набора строк или команды.  
  
*BindType*<br/>
Единица хранения для сведения о привязке. По умолчанию используется `ATLBINDINGS` структуры (см. в разделе atldb.h).  
  
*BindingVector*<br/>
Единица хранения сведений о столбце. По умолчанию используется [CAtlMap](../../atl/reference/catlmap-class.md) где ключевым элементом является значением HACCESSOR, а значение элемента — это указатель на `BindType` структуры.  
  
## <a name="requirements"></a>Требования  

**Заголовок:** atldb.h  

## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[IAccessorImpl](#iaccessorimpl)|Конструктор.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[AddRefAccessor](#addrefaccessor)|Добавляет счетчик ссылок в существующий метод доступа.|  
|[CreateAccessor](#createaccessor)|Создает метод доступа на основе набора привязок.|  
|[GetBindings](#getbindings)|Возвращает привязки из метода доступа.|  
|[ReleaseAccessor](#releaseaccessor)|Освобождает метод доступа.|  
  
## <a name="remarks"></a>Примечания  

Обязателен для наборов строк и команд. OLE DB требует, чтобы поставщики для реализации HACCESSOR, который является тегом в массив [DBBINDING](/previous-versions/windows/desktop/ms716845) структуры. Предоставляемые HACCESSORs `IAccessorImpl` являются адресами `BindType` структуры. По умолчанию `BindType` определяется как `ATLBINDINGS` в `IAccessorImpl`в определении шаблона. `BindType` предоставляет механизм, используемый `IAccessorImpl` для отслеживания числа элементов в его `DBBINDING` массива, а также ссылка метода доступа и число флагов.  

## <a name="iaccessorimpl"></a> IAccessorImpl::IAccessorImpl

Конструктор.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
IAccessorImpl();  
```  

## <a name="addrefaccessor"></a> IAccessorImpl::AddRefAccessor

Добавляет счетчик ссылок в существующий метод доступа.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IAccessor::AddRefAccessor](/previous-versions/windows/desktop/ms714978) в *справочнике программиста OLE DB*.

## <a name="createaccessor"></a> IAccessorImpl::CreateAccessor

Создает метод доступа на основе набора привязок.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,  
   DBCOUNTITEM cBindings,  
   const DBBINDING rgBindings[],  
   DBLENGTH cbRowSize,  
   HACCESSOR* phAccessor,  
   DBBINDSTATUS rgStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IAccessor::CreateAccessor](/previous-versions/windows/desktop/ms720969) в *справочнике программиста OLE DB*.  

## <a name="getbindings"></a> IAccessorImpl::GetBindings

Возвращает привязки базовые столбцы из объекта-получателя в метод доступа.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IAccessor::GetBindings](/previous-versions/windows/desktop/ms721253) в *справочнике программиста OLE DB*. 

## <a name="releaseaccessor"></a> IAccessorImpl::ReleaseAccessor

Освобождает метод доступа.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IAccessor::ReleaseAccessor](/previous-versions/windows/desktop/ms719717) в *справочнике программиста OLE DB*.
  
## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)