---
title: "Класс IPropertyPage2Impl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 43680d12febbd94137009f66242198129d4b3630
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypage2impl-class"></a>Класс IPropertyPage2Impl
Этот класс реализует **IUnknown** и наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPropertyPage2Impl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Указывает, какой элемент управления свойства получит фокус при активации страницы свойств. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) расширяет интерфейс [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) , добавив `EditProperty` метод. Этот метод позволяет клиенту выбрать конкретного свойства в объект страницы свойств.  
  
 Класс `IPropertyPage2Impl` просто возвращает **E_NOTIMPL** для **IPropertyPage2::EditProperty**. Тем не менее, он наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 При создании страницы свойств класса обычно является производным от `IPropertyPageImpl`. Для дополнительной поддержки **IPropertyPage2**, измените определение класса и переопределить `EditProperty` метод.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 Указывает, какой элемент управления свойства получит фокус при активации страницы свойств.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

