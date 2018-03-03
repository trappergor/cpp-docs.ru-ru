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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fbd91deb1d80c49dd403e8e08cc50f5fd8c8ec3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idochostuihandlerdispatch-interface"></a>Интерфейс IDocHostUIHandlerDispatch
Интерфейс для синтаксического анализа Microsoft HTML и механизм визуализации.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
> [!NOTE]
>  По ссылкам в следующей таблице, INet SDK справочных разделов для членов [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) интерфейса. `IDocHostUIHandlerDispatch`имеет ту же функциональность, что **IDocUIHostHandler**, отличие состоит, `IDocHostUIHandlerDispatch` является диспетчерский интерфейс, тогда как **IDocUIHostHandler** -это пользовательский интерфейс.  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115). Также вызывается, когда модальный пользовательский Интерфейс отображает MSHTML.|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Вызывается на узле с MSHTML, чтобы разрешить основному приложению заменить объект данных MSHTML.|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Вызывается MSHTML при его использовании в качестве конечного расположения сброса, чтобы разрешить основному приложению предоставить альтернативный интерфейс [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Вызывается средой MSHTML для получения интерфейса IDispatch поставщика услуг размещения.|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|Возвращает возможности пользовательского интерфейса узла MSHTML.|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Возвращает раздел реестра, в котором MSHTML хранятся пользовательские настройки.|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Вызывается при удалении MSHTML меню и панели инструментов.|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Вызывается из MSHTML, чтобы отобразить контекстное меню.|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Предоставляет узлу возможность заменить MSHTML меню и панелей инструментов.|  
|[Метод TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Вызывается методом MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) или [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) вызывается.|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Вызывается средой MSHTML, чтобы разрешить ведущему приложению изменять URL-адрес для загрузки.|  
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Уведомляет основное приложение об изменении состояния команды.|  
  
## <a name="remarks"></a>Примечания  
 Узел можно заменить меню, панелей инструментов и контекстные меню, используемые разбор Microsoft HTML и механизм визуализации (MSHTML), реализовав этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 Определение этого интерфейса доступна как IDL или C++, как показано ниже.  
  
|Определение типа|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|См (также входит в состав ATLBase.h)|  
  
## <a name="see-also"></a>См. также  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)









