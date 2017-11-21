---
title: "Класс ISpecifyPropertyPagesImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs: C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17eb3b81a662ea8d0d3a2b5871441e18840efc57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ispecifypropertypagesimpl-class"></a>Класс ISpecifyPropertyPagesImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Заполняет значения подсчета массива UUID. Каждый идентификатор UUID соответствует CLSID для одного из страницы свойств, которые могут быть отображены в окне свойств объекта.|  
  
## <a name="remarks"></a>Примечания  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейс позволяет клиенту получить список идентификаторов CLSID для страницы свойств, поддерживаемые объектом. Класс `ISpecifyPropertyPagesImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
> [!NOTE]
>  Не предоставляйте **ISpecifyPropertyPages** интерфейс, если объект не поддерживает страницы свойств.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages  
 Заполняет массив [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) структуру с CLSID для страниц свойств, которые могут быть отображены в окне свойств объекта.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для получения каждого CLSID.  
  
 В разделе [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)   
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
