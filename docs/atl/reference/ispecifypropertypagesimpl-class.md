---
title: Класс ISpecifyPropertyPagesImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b54b8e4fdfbbfd282475ed0ca6e221d826953cad
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879576"
---
# <a name="ispecifypropertypagesimpl-class"></a>Класс ISpecifyPropertyPagesImpl
Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейс.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Заполняет значения подсчета массив UUID. Каждый UUID соответствует CLSID для одного из страницы свойств, которые могут отображаться в окне свойств объекта.|  
  
## <a name="remarks"></a>Примечания  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейс позволяет клиенту получить список идентификаторов CLSID для страниц свойств, поддерживаемых объектом. Класс `ISpecifyPropertyPagesImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
> [!NOTE]
>  Не предоставляйте `ISpecifyPropertyPages` интерфейс, если объект поддерживает страницы свойств.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 Заполняет массив [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) структуру с CLSID для страниц свойств, которые могут отображаться в окне свойств объекта.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для получения каждого CLSID.  
  
 См. в разделе [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)   
 [Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
