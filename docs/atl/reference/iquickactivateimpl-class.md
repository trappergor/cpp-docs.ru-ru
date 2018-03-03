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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6f5bc1798bc8ec40fb6f6d9d22f48c06b19745
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iquickactivateimpl-class"></a>Класс IQuickActivateImpl
Этот класс объединяет инициализации элементов управления контейнеров, в один вызов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IQuickActivateImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Возвращает текущий размер изображения для элемента управления на выполнение.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Выполняет быстрый инициализацию загружаемых элементов управления.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Информирует элемент управления контейнера, которая назначена его о том, сколько места на экране.|  
  
## <a name="remarks"></a>Примечания  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) интерфейс помогает избежать задержек при загрузке элементов управления, объединяя инициализации в рамках одного вызова контейнеров. `QuickActivate` Метод предоставляет контейнеру возможность передать указатель на [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) требуется структура, которая хранит указатели на все интерфейсы управления. При возвращении элемента управления передается обратно указатель [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структуру, которая хранит указатели на собственных интерфейсов, которые используются в качестве контейнера. Класс `IQuickActivateImpl` предоставляет реализацию по умолчанию **IQuickActivate** и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 Возвращает текущий размер изображения для элемента управления на выполнение.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер для полного отрисовки элемента управления и указывается в единицах HIMETRIC.  
  
 В разделе [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) в Windows SDK.  
  
##  <a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 Выполняет быстрый инициализацию загружаемых элементов управления.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Примечания  
 Эта структура содержит указатели на интерфейсы, необходимые для управления и значения некоторых свойств окружения. По возвращении, элемент управления передает указатель на [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структура, содержащая указатели на собственных интерфейсов, которые требует контейнер и дополнительных сведений о состоянии.  
  
 В разделе [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) в Windows SDK.  
  
##  <a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 Информирует элемент управления контейнера, которая назначена его о том, сколько места на экране.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер указывается в единицах HIMETRIC.  
  
 В разделе [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
