---
title: "IAxWinHostWindow Interface | Microsoft Docs"
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
  - "IAxWinHostWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindow interface"
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindow Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот интерфейс предоставляет методы для работы с элемента управления и его объект узла.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
interface IAxWinHostWindow : IUnknown  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[AttachControl](../Topic/IAxWinHostWindow::AttachControl.md)|Вложение существующий элемент управления к объекту основного приложения.|  
|[CreateControl](../Topic/IAxWinHostWindow::CreateControl.md)|Создает вложение элемента управления и его к объекту основного приложения.|  
|[CreateControlEx](../Topic/IAxWinHostWindow::CreateControlEx.md)|Создает элемент управления, вложение его к объекту основного приложения, и при необходимости настраивает обработчик событий.|  
|[QueryControl](../Topic/IAxWinHostWindow::QueryControl.md)|Получает указатель интерфейса на элемент управления.|  
|[SetExternalDispatch](../Topic/IAxWinHostWindow::SetExternalDispatch.md)|Задает внешний интерфейс `IDispatch`.|  
|[SetExternalUIHandler](../Topic/IAxWinHostWindow::SetExternalUIHandler.md)|Задает внешний интерфейс `IDocHostUIHandlerDispatch`.|  
  
## Заметки  
 Этот интерфейс предоставить элемент управления ActiveX библиотеки ATL при размещении объекты.  Вызовите методы в этом интерфейсе, чтобы создать или вложить элемент управления к объекту основного приложения, чтобы получить интерфейс из размещенного элемента управления или задавать внешние диспетчерский интерфейс или обработчик пользовательского интерфейса для использования при размещении веб\-браузера.  
  
## Требования  
 Определение этого интерфейса доступен как IDL или C\+\+, как показано ниже.  
  
|Тип определения|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(также включается в ATLBase.h\)|  
  
## См. также  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)