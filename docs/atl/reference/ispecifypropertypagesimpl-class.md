---
title: "Класс ISpecifyPropertyPagesImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
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
ms.openlocfilehash: 4d5f74de2ec6569527221cf94df6f7921f4bb4c9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ispecifypropertypagesimpl-class"></a>Класс ISpecifyPropertyPagesImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Заполняет значения подсчета массива UUID. Каждый UUID соответствует идентификатор CLSID для одного из свойств, которые могут отображаться в окне свойств объекта.|  
  
## <a name="remarks"></a>Примечания  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейс позволяет клиенту получить список CLSID для страниц свойств, поддерживаемых объектом. Класс `ISpecifyPropertyPagesImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
> [!NOTE]
>  Не предоставляйте **ISpecifyPropertyPages** интерфейс, если объект не поддерживает страницы свойств.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages  
 Заполняет массив [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) структуру с CLSID для страниц свойств, которые могут отображаться в окне свойств объекта.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Примечания  
 ATL используется сопоставление свойств объекта для извлечения каждой CLSID.  
  
 В разделе [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)   
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

