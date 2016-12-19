---
title: "IAxWinAmbientDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinAmbientDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatch interface"
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinAmbientDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот интерфейс предоставляет методы для определения характеристик управления или контейнера.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
interface IAxWinAmbientDispatch : IDispatch  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[get\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::get_AllowContextMenu.md)|Свойство разрешено **AllowContextMenu** указывающее, находится ли размещенный элемент управления для отображения своего собственного контекстного меню.|  
|[get\_AllowShowUI](../Topic/IAxWinAmbientDispatch::get_AllowShowUI.md)|Свойство разрешено **AllowShowUI** указывающее, находится ли размещенный элемент управления для отображения своего собственного пользовательского интерфейса.|  
|[get\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::get_AllowWindowlessActivation.md)|Свойство **AllowWindowlessActivation** указывающее, будет ли контейнер давать безоконная активация.|  
|[get\_BackColor](../Topic/IAxWinAmbientDispatch::get_BackColor.md)|Свойство `BackColor` задает цвет фона окружения контейнера.|  
|[get\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::get_DisplayAsDefault.md)|**DisplayAsDefault** внешнее свойство, которое позволяет элементу управления, чтобы выяснить, если элемент управления по умолчанию.|  
|[get\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::get_DocHostDoubleClickFlags.md)|Свойство **DocHostDoubleClickFlags** определяет операцию, которая должна выполняться в ответ на дважды щелкнуть.|  
|[get\_DocHostFlags](../Topic/IAxWinAmbientDispatch::get_DocHostFlags.md)|Свойство **DocHostFlags** определяет возможности пользовательского интерфейса объекта основного приложения.|  
|[get\_Font](../Topic/IAxWinAmbientDispatch::get_Font.md)|Свойство **Шрифт** определяет внешний шрифт контейнера.|  
|[get\_ForeColor](../Topic/IAxWinAmbientDispatch::get_ForeColor.md)|Свойство `ForeColor` задает цвет внешнего контейнера.|  
|[get\_LocaleID](../Topic/IAxWinAmbientDispatch::get_LocaleID.md)|Свойство **LocaleID** определяет внешний код языка контейнера.|  
|[get\_MessageReflect](../Topic/IAxWinAmbientDispatch::get_MessageReflect.md)|**MessageReflect** Внешнее свойство определяет, следует ли автоматически задает контейнер сообщения к элементу управления.|  
|[get\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::get_OptionKeyPath.md)|Свойство **OptionKeyPath** задает путь к разделу реестра с параметрами пользователя.|  
|[get\_ShowGrabHandles](../Topic/IAxWinAmbientDispatch::get_ShowGrabHandles.md)|Свойство **ShowGrabHandles** внешнее позволяет элементу управления, чтобы выяснить, если оно должно рисует с маркерами захвата.|  
|[get\_ShowHatching](../Topic/IAxWinAmbientDispatch::get_ShowHatching.md)|Свойство **ShowHatching** внешнее позволяет элементу управления, чтобы выяснить, если оно должно рисует насидело.|  
|[get\_UserMode](../Topic/IAxWinAmbientDispatch::get_UserMode.md)|Свойство окружения **UserMode** определяет пользовательский режим контейнера.|  
|[put\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::put_AllowContextMenu.md)|Свойство разрешено **AllowContextMenu** указывающее, находится ли размещенный элемент управления для отображения своего собственного контекстного меню.|  
|[put\_AllowShowUI](../Topic/IAxWinAmbientDispatch::put_AllowShowUI.md)|Свойство разрешено **AllowShowUI** указывающее, находится ли размещенный элемент управления для отображения своего собственного пользовательского интерфейса.|  
|[put\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::put_AllowWindowlessActivation.md)|Свойство **AllowWindowlessActivation** указывающее, будет ли контейнер давать безоконная активация.|  
|[put\_BackColor](../Topic/IAxWinAmbientDispatch::put_BackColor.md)|Свойство `BackColor` задает цвет фона окружения контейнера.|  
|[put\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::put_DisplayAsDefault.md)|**DisplayAsDefault** внешнее свойство, которое позволяет элементу управления, чтобы выяснить, если элемент управления по умолчанию.|  
|[put\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::put_DocHostDoubleClickFlags.md)|Свойство **DocHostDoubleClickFlags** определяет операцию, которая должна выполняться в ответ на дважды щелкнуть.|  
|[put\_DocHostFlags](../Topic/IAxWinAmbientDispatch::put_DocHostFlags.md)|Свойство **DocHostFlags** определяет возможности пользовательского интерфейса объекта основного приложения.|  
|[put\_Font](../Topic/IAxWinAmbientDispatch::put_Font.md)|Свойство **Шрифт** определяет внешний шрифт контейнера.|  
|[put\_ForeColor](../Topic/IAxWinAmbientDispatch::put_ForeColor.md)|Свойство `ForeColor` задает цвет внешнего контейнера.|  
|[put\_LocaleID](../Topic/IAxWinAmbientDispatch::put_LocaleID.md)|Свойство **LocaleID** определяет внешний код языка контейнера.|  
|[put\_MessageReflect](../Topic/IAxWinAmbientDispatch::put_MessageReflect.md)|**MessageReflect** Внешнее свойство определяет, следует ли автоматически задает контейнер сообщения к элементу управления.|  
|[put\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::put_OptionKeyPath.md)|Свойство **OptionKeyPath** задает путь к разделу реестра с параметрами пользователя.|  
|[put\_UserMode](../Topic/IAxWinAmbientDispatch::put_UserMode.md)|Свойство окружения **UserMode** определяет пользовательский режим контейнера.|  
  
## Заметки  
 Этот интерфейс предоставить элемент управления ActiveX библиотеки ATL при размещении объекты.  Вызовите методы для этого интерфейса для задания свойств внешнего доступа к элементу управления размещенного или указать другие аспекты расширения функциональности контейнера.  Дополнить свойства, указанного `IAxWinAmbientDispatch`, использует [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) пытается загрузить сведения о типе для `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из typelib, содержащий код.  
  
 При связывании с ATL90.dll, то **AXHost** загрузит сведения о типе из typelib в DLL.  
  
 Дополнительные сведения см. в разделе [Размещение элементов управления ActiveX с использованием библиотеки ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md).  
  
## Требования  
 Определение этого интерфейса доступен в нескольких форм, как показано в таблице ниже.  
  
|Тип определения|Файл|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Библиотека типов|ATL.dll|  
|C\+\+|atliface.h \(также включается в ATLBase.h\)|  
  
## См. также  
 [IAxWinAmbientDispatchEx Interface](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow Interface](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)