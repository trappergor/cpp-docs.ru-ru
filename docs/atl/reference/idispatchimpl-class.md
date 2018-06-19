---
title: Класс IDispatchImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fddf556eba07264f6ea0b01edea3e3d1e8a3a7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364370"
---
# <a name="idispatchimpl-class"></a>Класс IDispatchImpl
Предоставляет реализацию по умолчанию для `IDispatch` частью сдвоенный интерфейс.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `T`  
 Сдвоенный интерфейс.  
  
 [in] `piid`  
 Указатель на IID `T`.  
  
 [in] `plibid`  
 Указатель на идентификатор LIBID библиотеки типов, содержащий сведения об интерфейсе. По умолчанию передается библиотеки типов на уровне сервера.  
  
 [in] `wMajor`  
 Основной номер версии для библиотеки типов. По умолчанию значение равно 1.  
  
 [in] `wMinor`  
 Дополнительный номер версии для библиотеки типов. По умолчанию значение равно 0.  
  
 [in] `tihclass`  
 Класс, используемый для управления сведения о типе `T`. Значение по умолчанию `CComTypeInfoHolder`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Конструктор. Вызовы `AddRef` для защищенного члена переменной, которая управляет данными типа сдвоенный интерфейс. Деструктор вызывает `Release`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Сопоставляет набор имен соответствующему набору идентификаторов диспетчеризации.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Извлекает сведения о типе для сдвоенный интерфейс.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Определяет, существует ли сведения о типе для сдвоенный интерфейс.|  
|[IDispatchImpl::Invoke](#invoke)|Предоставляет доступ к методам и свойствам, предоставляемым сдвоенный интерфейс.|  
  
## <a name="remarks"></a>Примечания  
 `IDispatchImpl` предоставляет реализацию по умолчанию для `IDispatch` частью любой сдвоенный интерфейс для объекта. Сдвоенный интерфейс является производным от `IDispatch` и использует только типы, совместимые с Automation. Как и disp-интерфейса сдвоенный интерфейс поддерживает связывание раннее и позднее связывание; Тем не менее сдвоенный интерфейс поддерживает также связывание vtable.  
  
 Пример типичной реализации `IDispatchImpl`.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 По умолчанию `IDispatchImpl` класс осуществляет поиск сведений о типе `T` в реестре. Чтобы реализовать Незарегистрированный интерфейс, можно использовать `IDispatchImpl` класс без доступа к реестру с помощью стандартных номер_версии. При создании `IDispatchImpl` объект, имеющий значение 0xFFFF `wMajor` до 0xFFFF как значение для `wMinor`, `IDispatchImpl` класс извлекает библиотеку типов из DLL-файл вместо реестра.  
  
 `IDispatchImpl` содержит статический член типа `CComTypeInfoHolder` , управляющий сведения о типе для сдвоенный интерфейс. Если у вас есть несколько объектов, реализующих же два интерфейса, только один экземпляр `CComTypeInfoHolder` используется.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getidsofnames"></a>  IDispatchImpl::GetIDsOfNames  
 Сопоставляет набор имен соответствующему набору идентификаторов диспетчеризации.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [:: GetIdsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) в Windows SDK.  
  
##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo  
 Извлекает сведения о типе для сдвоенный интерфейс.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) в Windows SDK.  
  
##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount  
 Определяет, существует ли сведения о типе для сдвоенный интерфейс.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе `IDispatch::GetTypeInfoCount` в Windows SDK.  
  
##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl  
 Конструктор. Вызовы `AddRef` для защищенного члена переменной, которая управляет данными типа сдвоенный интерфейс. Деструктор вызывает **выпуска**.  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>  IDispatchImpl::Invoke  
 Предоставляет доступ к методам и свойствам, предоставляемым сдвоенный интерфейс.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
