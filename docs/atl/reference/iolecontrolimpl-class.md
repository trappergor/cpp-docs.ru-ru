---
title: "IOleControlImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleControlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOleControlImpl class"
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IOleControlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию по умолчанию для интерфейса **IOleControl** и реализует **IUnknown**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IOleControlImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IOleControlImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IOleControlImpl::FreezeEvents](../Topic/IOleControlImpl::FreezeEvents.md)|Указывает, пропускается ли контейнер или принимает события из элемента управления.|  
|[IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md)|Заполняет сведения о расширениях функциональности ввода элемента управления.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](../Topic/IOleControlImpl::OnAmbientPropertyChange.md)|Уведомляет элемент управления, что одно или несколько свойств контейнера изменении окружения.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IOleControlImpl::OnMnemonic](../Topic/IOleControlImpl::OnMnemonic.md)|Уведомляет элемент управления, что пользователь отжимал указанный нажатие клавиши.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Класс `IOleControlImpl` предоставляет реализацию по умолчанию для интерфейса [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [IOleObjectImpl Class](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)