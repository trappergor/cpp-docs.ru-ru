---
title: Класс IPersistPropertyBagImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09b0acfc1fc1f9147a6acbe8bbfe66016dc0b54b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201706"
---
# <a name="ipersistpropertybagimpl-class"></a>Класс IPersistPropertyBagImpl
Этот класс реализует `IUnknown` и позволяет сохранить его свойства в контейнер свойств, предоставляемых клиентом объекту.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Инициализирует только что созданный объект. Реализация ATL, возвращается значение s_ок.|  
|[IPersistPropertyBagImpl::Load](#load)|Загружает свойства объекта из контейнера свойств, предоставляемых клиентом.|  
|[IPersistPropertyBagImpl::Save](#save)|Сохраняет свойства объекта в контейнер свойств, предоставляемых клиентом.|  
  
## <a name="remarks"></a>Примечания  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) интерфейс позволяет объекту сохранить свои свойства в контейнер свойств, предоставляемых клиентом. Класс `IPersistPropertyBagImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 `IPersistPropertyBag` работает в сочетании с [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) и [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Эти последний два интерфейса должен быть реализован с помощью клиента. Через `IPropertyBag`, клиент сохраняет и загружает отдельных свойств объекта. Через `IErrorLog`, объект и на клиенте можно сообщить о каких-либо ошибок.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID  
 Извлекает идентификатор CLSID объекта.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.  
  
##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew  
 Инициализирует только что созданный объект.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) в Windows SDK.  
  
##  <a name="load"></a>  IPersistPropertyBagImpl::Load  
 Загружает свойства объекта из контейнера свойств, предоставляемых клиентом.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для извлечения этой информации.  
  
 См. в разделе [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) в Windows SDK.  
  
##  <a name="save"></a>  IPersistPropertyBagImpl::Save  
 Сохраняет свойства объекта в контейнер свойств, предоставляемых клиентом.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для хранения подобной информации. По умолчанию этот метод сохраняет все свойства, независимо от значения *fSaveAllProperties*.  
  
 См. в разделе [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
