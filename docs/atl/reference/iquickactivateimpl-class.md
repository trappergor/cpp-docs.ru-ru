---
title: Класс IQuickActivateImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9131a1cc1f8d0c66f2eb3616f4903db74ea4bdf0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881377"
---
# <a name="iquickactivateimpl-class"></a>Класс IQuickActivateImpl
Этот класс объединяет инициализации элемента управления контейнеры в один вызов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IQuickActivateImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Извлекает текущий размер изображения для выполнения элемента управления.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Выполняет быстрый инициализацию загружаемых элементов управления.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Информирует элемент управления контейнера, были назначены какой объем места на экране.|  
  
## <a name="remarks"></a>Примечания  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) интерфейс помогает избежать задержек при загрузке элементов управления путем объединения инициализации в одном вызове контейнеры. `QuickActivate` Метод позволяет контейнеру передавать указатель на [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) требуется структура, которая хранит указатели на все интерфейсы управления. При возвращении управления передает указатель на [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структуру, которая хранит указатели на собственных интерфейсов, которые используются в качестве контейнера. Класс `IQuickActivateImpl` предоставляет реализацию по умолчанию `IQuickActivate` и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent  
 Извлекает текущий размер изображения для выполнения элемента управления.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер для полной подготовки к просмотру элемента управления и указывается в единицах HIMETRIC.  
  
 См. в разделе [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) в Windows SDK.  
  
##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate  
 Выполняет быстрый инициализацию загружаемых элементов управления.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Примечания  
 Эта структура содержит указатели на интерфейсы, необходимые для управления и значения некоторых свойств окружения. При возврате управления передает указатель на [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) структуру, которая содержит указатели на собственных интерфейсов, необходимых для контейнера, а также дополнительные сведения о состоянии.  
  
 См. в разделе [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) в Windows SDK.  
  
##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent  
 Информирует элемент управления контейнера, были назначены какой объем места на экране.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Примечания  
 Размер указывается в единицах HIMETRIC.  
  
 См. в разделе [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
