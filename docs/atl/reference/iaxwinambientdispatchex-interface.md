---
title: "IAxWinAmbientDispatchEx Interface | Microsoft Docs"
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
  - "ATL.IAxWinAmbientDispatchEx"
  - "IAxWinAmbientDispatchEx"
  - "ATL::IAxWinAmbientDispatchEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatchEx interface"
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinAmbientDispatchEx Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот интерфейс реализуется дополнительные внешние свойства для размещаемого элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      MIDL_INTERFACE( "B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5" )  
IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[SetAmbientDispatch](../Topic/IAxWinAmbientDispatchEx::SetAmbientDispatch.md)|Этот метод вызывается, чтобы дополнить по умолчанию внешний интерфейс определяемые пользователем свойства с интерфейсом.|  
  
## Заметки  
 Включите этот интерфейс в приложениях, которые статически связаны на библиотеку ATL и хозяйничают управления ActiveX, особенно в элементах управления библиотеки ATL ActiveX, которые имеют внешние свойства.  Включая этот интерфейс не отдает это утверждение: "Вы забыли передать идентификатор LIBID к CComModule::Init?"  
  
 Этот интерфейс предоставить элемент управления ActiveX библиотеки ATL при размещении объекты.  Производный от [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` добавляет метод, который позволяет дополнить внешний интерфейс свойства предоставленный библиотеки ATL с одним из требований.  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) пытается загрузить сведения о типе для `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, содержащая код.  
  
 При связывании с ATL90.dll, то **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.  
  
 Дополнительные сведения см. в разделе [Размещение элементов управления ActiveX с использованием библиотеки ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md).  
  
## Требования  
 Определение этого интерфейса доступен в нескольких форм, как показано в следующей таблице.  
  
|Тип определения|Файл|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Библиотека типов|ATL.dll|  
|C\+\+|atliface.h \(также включается в ATLBase.h\)|  
  
## См. также  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)