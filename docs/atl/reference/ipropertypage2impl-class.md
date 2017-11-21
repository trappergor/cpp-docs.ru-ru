---
title: "Класс IPropertyPage2Impl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs: C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 40cdaeef31226cf47dcf4beb08f11242932578c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ipropertypage2impl-class"></a>Класс IPropertyPage2Impl
Этот класс реализует **IUnknown** и наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
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
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) расширяет интерфейс [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) путем добавления `EditProperty` метод. Этот метод позволяет клиенту выбрать конкретное свойство в объект страницы свойств.  
  
 Класс `IPropertyPage2Impl` просто возвращает **E_NOTIMPL** для **IPropertyPage2::EditProperty**. Тем не менее, он наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 При создании страницы свойств класса, обычно является производным от `IPropertyPageImpl`. Дополнительную поддержки **IPropertyPage2**, измените определение этого класса и переопределить `EditProperty` метод.  
  
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
 В разделе [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
