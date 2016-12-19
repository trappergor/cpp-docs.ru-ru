---
title: "IOleInPlaceObjectWindowlessImpl Class | Microsoft Docs"
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
  - "IOleInPlaceObjectWindowlessImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activation [C++], ATL - библиотека"
  - "элементы управления ActiveX [C++], communication between container and control"
  - "элементы управления [ATL], windowless"
  - "deactivating ATL"
  - "IOleInPlaceObjectWindowless, ATL -реализация"
  - "IOleInPlaceObjectWindowlessImpl class"
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleInPlaceObjectWindowlessImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и предоставляет методы, позволяющие безоконный элемент управления для получения сообщений окна и участвовать в операциях перетаскивания.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceObjectWindowlessImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IOleInPlaceObjectWindowlessImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](../Topic/IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp.md)|Обеспечивает контекстную справку.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](../Topic/IOleInPlaceObjectWindowlessImpl::GetDropTarget.md)|Предоставляет интерфейс `IDropTarget` для активного в\- размещения, безоконного объекта, поддержки перетащите и удалить.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](../Topic/IOleInPlaceObjectWindowlessImpl::GetWindow.md)|Получает дескриптор окна.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate.md)|Деактивирует активное элемент управления в\- размещения.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](../Topic/IOleInPlaceObjectWindowlessImpl::OnWindowMessage.md)|Отправляет сообщение в безоконному из контейнера элемент управления, который активно в\- размещения.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](../Topic/IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo.md)|Повторно активирует ранее выключенный элемент управления.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](../Topic/IOleInPlaceObjectWindowlessImpl::SetObjectRects.md)|Указывает, какая часть управления в\- размещения видимой.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::UIDeactivate.md)|Завершает работу и удаляется пользовательского интерфейса обозреватель. эта встроенная активация|  
  
## Заметки  
 Интерфейс [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) управляет возобновление и деактивация элементов управления в\- размещения и определяет, какая часть элемента управления должно быть видимо.  Интерфейс [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) позволяет безоконный элемент управления для получения сообщений окна и участвовать в операциях перетаскивания.  Класс `IOleInPlaceObjectWindowlessImpl` предоставляет реализацию по умолчанию `IOleInPlaceObject` и `IOleInPlaceObjectWindowless` и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)