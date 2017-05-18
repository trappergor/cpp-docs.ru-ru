---
title: "Класс IPersistPropertyBagImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: abef2ffa759cf74ee2316c7e0c9dd84f5c76b1d7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="ipersistpropertybagimpl-class"></a>Класс IPersistPropertyBagImpl
Этот класс реализует **IUnknown** и позволяет сохранить его свойств в контейнер свойств, предоставленное клиентом объекту.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Инициализирует только что созданный объект. Возвращает реализацию ATL `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Загружает свойства объекта из контейнера свойств, предоставленное клиентом.|  
|[IPersistPropertyBagImpl::Save](#save)|Сохраняет свойства объекта в контейнер свойств, предоставленное клиентом.|  
  
## <a name="remarks"></a>Примечания  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) интерфейс позволяет объекту сохранить его свойств в контейнер свойств, предоставленное клиентом. Класс `IPersistPropertyBagImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **IPersistPropertyBag** работает в сочетании с [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) и [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Эти последние два интерфейса должен быть реализован клиентом. Через `IPropertyBag`, клиент сохраняет и загружает отдельных свойств объекта. Через **IErrorLog**, и объект и клиент может сообщать все обнаруженные ошибки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Извлекает идентификатор CLSID объекта.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Инициализирует только что созданный объект.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="load"></a>IPersistPropertyBagImpl::Load  
 Загружает свойства объекта из контейнера свойств, предоставленное клиентом.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для получения этих сведений.  
  
 В разделе [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="save"></a>IPersistPropertyBagImpl::Save  
 Сохраняет свойства объекта в контейнер свойств, предоставленное клиентом.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для хранения этой информации. По умолчанию этот метод сохраняет все свойства, независимо от значения *fSaveAllProperties*.  
  
 В разделе [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

