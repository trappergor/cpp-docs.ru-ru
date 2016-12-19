---
title: "CAxWindow Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAxWindowT"
  - "CAxWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, размещение элементов управления ActiveX"
  - "CAxWindow class"
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для работы с окно при размещении элемента управления ActiveX.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CAxWindow : public CWindow  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[AttachControl](../Topic/CAxWindow::AttachControl.md)|Вложение существующий элемент управления ActiveX на объект `CAxWindow`.|  
|[CAxWindow](../Topic/CAxWindow::CAxWindow.md)|Создает объект `CAxWindow`.|  
|[CreateControl](../Topic/CAxWindow::CreateControl.md)|Создает элемент управления ActiveX, инициализирует и размещение его в окне `CAxWindow`.|  
|[CreateControlEx](../Topic/CAxWindow::CreateControlEx.md)|Создает элемент управления ActiveX и получает указатель интерфейса \(или указатели\) из элемента управления.|  
|[GetWndClassName](../Topic/CAxWindow::GetWndClassName.md)|\(Статический\) Извлекает предопределенное имя класса объекта `CAxWindow`.|  
|[QueryControl](../Topic/CAxWindow::QueryControl.md)|Извлекает **IUnknown** элемент управления ActiveX.|  
|[QueryHost](../Topic/CAxWindow::QueryHost.md)|Извлекает указатель **IUnknown** объекта `CAxWindow`.|  
|[SetExternalDispatch](../Topic/CAxWindow::SetExternalDispatch.md)|Задает внешний интерфейс диспетчера используемый объектом `CAxWindow`.|  
|[SetExternalUIHandler](../Topic/CAxWindow::SetExternalUIHandler.md)|Задает внешний интерфейс **IDocHostUIHandler** используемый объектом `CAxWindow`.|  
  
### Операторы  
  
|||  
|-|-|  
|[оператор \=](../Topic/CAxWindow::operator%20=.md)|Присвоит **HWND**  к существующему объекту **CAxWindow**.|  
  
## Заметки  
 Этот класс содержит методы для работы с окно, размещение элемент управления ActiveX.  Размещение оно предоставляется "**AtlAxWin80"**, который создает программу\-оболочку `CAxWindow`.  
  
 Класс `CAxWindow` реализован как специализация класса `CAxWindowT`.  Эта специализация объявлена как:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Если необходимо изменить базовый класс можно использовать `CAxWindowT` и указав новый базовый класс в качестве аргумента шаблона.  
  
## Требования  
 **Header:** atlwin.h  
  
## См. также  
 [Образец ATLCON](../../top/visual-cpp-samples.md)   
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [Основные сведения о составном элементе управления](../Topic/ATL%20Composite%20Control%20Fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)