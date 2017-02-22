---
title: "IOleInPlaceActiveObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleInPlaceActiveObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], communication between container and control"
  - "IOleInPlaceActiveObject, ATL -реализация"
  - "IOleInPlaceActiveObjectImpl class"
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IOleInPlaceActiveObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для помощи в\- размещения сообщений между элементом управления и его контейнером.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceActiveObjectImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IOleInPlaceActiveObjectImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](../Topic/IOleInPlaceActiveObjectImpl::ContextSensitiveHelp.md)|Обеспечивает контекстную справку.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](../Topic/IOleInPlaceActiveObjectImpl::EnableModeless.md)|Включает безрежимные диалоговые окна.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](../Topic/IOleInPlaceActiveObjectImpl::GetWindow.md)|Получает дескриптор окна.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnDocWindowActivate.md)|Уведомляет элемент управления, когда активировано или деактивации окна документа контейнера.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnFrameWindowActivate.md)|Уведомляет элемент управления, когда активировано или деактивации фреймовое окно верхнего уровня контейнера.  Return реализации библиотеки ATL|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](../Topic/IOleInPlaceActiveObjectImpl::ResizeBorder.md)|Уведомляет элемент управления для этого требуется размер его границы.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](../Topic/IOleInPlaceActiveObjectImpl::TranslateAccelerator.md)|Обрабатывает сообщения сочетание клавиш меню из контейнера.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Связь голевых передач интерфейса [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) в\- размещения между элементом управления и его контейнером; например, связывающ активное состояние элемента управления и контейнера и числа элемент управления для этого требуется размер.  Класс `IOleInPlaceActiveObjectImpl` предоставляет реализацию по умолчанию `IOleInPlaceActiveObject` и поддерживает **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)