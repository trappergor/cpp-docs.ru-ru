---
title: "Composite Control Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "составные элементы управления, глобальные функции"
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Composite Control Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эти функции предоставляют поддержку для создания диалоговые окна, а также для создания, места и лицензирование элементов управления ActiveX.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Создание модального диалогового окна из шаблона диалогового окна предоставленное пользователем.  В результате откроется диалоговое окно может содержать элементы управления ActiveX.|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Создает безрежимное диалоговое окно из шаблона диалогового окна предоставленное пользователем.  В результате откроется диалоговое окно может содержать элементы управления ActiveX.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Создает элемент управления ActiveX, инициализирует и размещение его в определенном окне.|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Создает элемент управления ActiveX, инициализирует его, размещение его в определенном окне, и возвращает указатель интерфейса \(или указатели\) из элемента управления.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Создает лицензированное элемент управления ActiveX, инициализирует и размещение его в определенном окне.|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Создает лицензированное элемент управления ActiveX, инициализирует его, размещение его в определенном окне, и возвращает указатель интерфейса \(или указатели\) из элемента управления.|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Вложение ранее созданный элемент управления к определенному окну.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Используемый, чтобы получить непосредственный указатель интерфейса на контейнер для заданного окна \(если они есть\), заданное его дескриптор.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Используемый для получения непосредственно указатель интерфейса внутри элемента управления, которые содержат указанное окно \(если они есть\), заданное его дескриптор.|  
|[AtlSetChildSite](../Topic/AtlSetChildSite.md)|Инициализирует **IUnknown** подчиненного сайта.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Инициализирует код размещения для объектов AxWin.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Uninitializes код размещения для объектов AxWin.|  
|[AtlGetObjectSourceInterface](../Topic/AtlGetObjectSourceInterface.md)|Данные о возвращений по умолчанию интерфейсе источника объекта.|  
  
## См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Composite Control Macros](../../atl/reference/composite-control-macros.md)