---
title: "IPointerInactiveImpl Class | Microsoft Docs"
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
  - "IPointerInactiveImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inactive objects"
  - "IPointerInactive ATL implementation"
  - "IPointerInactiveImpl class"
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPointerInactiveImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и методы интерфейса [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IPointerInactiveImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPointerInactiveImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPointerInactiveImpl::GetActivationPolicy](../Topic/IPointerInactiveImpl::GetActivationPolicy.md)|Извлекает текущая политика активации для объекта.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](../Topic/IPointerInactiveImpl::OnInactiveMouseMove.md)|Уведомляет объект, перемещенный указатель мыши над ним, указывающее объект может создать события мыши.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](../Topic/IPointerInactiveImpl::OnInactiveSetCursor.md)|Задает указатель мыши для неактивного объекта.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Бездействующий объект, просто загрузить или выполнить.  В отличие от активный объект, бездействующий объект не может получить сообщения мыши и клавиатуры Windows.  Таким образом, неактивные объекты используют меньше ресурсов и обычно является более эффективным.  
  
 Интерфейс [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) позволяет объекту для поддержки минимальный уровень взаимодействия мыши еще остающ неактивен.  Эта функция особенно полезна для элементов управления.  
  
 Классифицируйте средства `IPointerInactiveImpl` методы `IPointerInactive` просто возвращать **E\_NOTIMPL**.  Однако в нем содержатся **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)