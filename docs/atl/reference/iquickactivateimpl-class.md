---
title: "Класс IQuickActivateImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4f6b75da64efa12e43fa160c57da4291acae03ca
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iquickactivateimpl-class"></a>Класс IQuickActivateImpl
Этот класс объединяет инициализации контейнеров элементов управления в один вызов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IQuickActivateImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Получает текущий размер изображения для выполнения элемента управления.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Выполняет инициализацию быстрого загружаемых элементов управления.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Информирует элемент управления контейнера назначены объем места на экране.|  
  
## <a name="remarks"></a>Примечания  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) интерфейс помогает избежать задержек при загрузке элементов управления путем объединения инициализации в одном вызове контейнеров. `QuickActivate` Метод позволяет контейнеру передать указатель на [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) требуется структура, которая содержит указатели на все интерфейсы управления. При возвращении управления передает указатель на [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структура, которая содержит указатели на собственных интерфейсов, которые используются в качестве контейнера. Класс `IQuickActivateImpl` предоставляет реализацию по умолчанию **IQuickActivate** и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 Получает текущий размер изображения для выполнения элемента управления.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер — для полного отображения элемента управления и указывается в единицах HIMETRIC.  
  
 В разделе [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 Выполняет инициализацию быстрого загружаемых элементов управления.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Примечания  
 Эта структура содержит указатели на интерфейсы, необходимые для управления и значения некоторых свойств окружения. При возврате управления передает указатель на [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структуру, которая содержит указатели на собственных интерфейсов, необходимые для контейнера, а также дополнительные сведения о состоянии.  
  
 В разделе [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 Информирует элемент управления контейнера назначены объем места на экране.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер указывается в единицах HIMETRIC.  
  
 В разделе [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

