---
title: "Интерфейс IDocHostUIHandlerDispatch | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: 22
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ba89697fb1c0e81d648d8faaaff1a97bb6a5d9ea
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="idochostuihandlerdispatch-interface"></a>Интерфейс IDocHostUIHandlerDispatch
Интерфейс для синтаксического анализа Microsoft HTML и механизм визуализации.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
> [!NOTE]
>  Ссылки в следующей таблице, являются INet SDK справочных разделов для членов [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) интерфейса. `IDocHostUIHandlerDispatch`выполняет те же функции, как **IDocUIHostHandler**, с тем отличием, что `IDocHostUIHandlerDispatch` является диспетчерский интерфейс, тогда как **IDocUIHostHandler** -это пользовательский интерфейс.  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115). Также вызывается, когда модальный пользовательский Интерфейс отображает MSHTML.|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Вызывается на узле с MSHTML позволит узлу MSHTML в объект данных.|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Вызывается MSHTML, когда он используется в качестве объекта-приемника позволяет ведущему приложению указать альтернативный [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Вызывается MSHTML для получения интерфейса IDispatch узла.|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|Возвращает возможности пользовательского интерфейса узла MSHTML.|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Возвращает раздел реестра, в котором MSHTML сохраняет настройки пользователя.|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Вызывается, когда MSHTML удаляет его меню и панели инструментов.|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Вызывается из MSHTML, чтобы отобразить контекстное меню.|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Позволяет основному приложению замените MSHTML меню и панели инструментов.|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Вызывается методом MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) или [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) вызывается.|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Вызывается MSHTML позволит узлу возможность изменить URL-адрес для загрузки.|  
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Уведомляет основное приложение об изменении состояния команды.|  
  
## <a name="remarks"></a>Примечания  
 Узел можно заменить меню, панелей инструментов и контекстные меню, используемые анализ Microsoft HTML и механизм визуализации (MSHTML) путем реализации этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Насколько (также входит в ATLBase.h)|  
  
## <a name="see-also"></a>См. также  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)










