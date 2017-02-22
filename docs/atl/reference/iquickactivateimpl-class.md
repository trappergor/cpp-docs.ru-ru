---
title: "IQuickActivateImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IQuickActivateImpl"
  - "ATL::IQuickActivateImpl<T>"
  - "ATL.IQuickActivateImpl"
  - "ATL.IQuickActivateImpl<T>"
  - "IQuickActivateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activating ATL controls"
  - "элементы управления [ATL], активация"
  - "IQuickActivate ATL implementation"
  - "IQuickActivateImpl class"
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IQuickActivateImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс объединяет инициализацию элемента управления контейнеров в отдельный вызов.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template<   
class T   
>  
class ATL_NO_VTABLE IQuickActivateImpl :  
public IQuickActivate  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IQuickActivateImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IQuickActivateImpl::GetContentExtent](../Topic/IQuickActivateImpl::GetContentExtent.md)|Извлекает текущий размер изображения по выполнению элемента управления.|  
|[IQuickActivateImpl::QuickActivate](../Topic/IQuickActivateImpl::QuickActivate.md)|Выполняет быструю инициализацию загружаемой элементов управления.|  
|[IQuickActivateImpl::SetContentExtent](../Topic/IQuickActivateImpl::SetContentExtent.md)|Уведомляет элемент управления, сколько места отображения контейнера присвоил на него.|  
  
## Заметки  
 Контейнеры интерфейса [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) помогает избежать задержки при управления загрузки путем объединения инициализацию в одном вызове.  Метод `QuickActivate` позволяет контейнеру передать указатель на структуру [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630), которая содержит указатели на всем интерфейсам необходимости элемента управления.  По возвращении элемент управления передает обратно указатель на структуру [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721), которая содержит указатели на собственным интерфейсы, используемые контейнером.  Класс `IQuickActivateImpl` предоставляет реализацию по умолчанию **IQuickActivate** и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)