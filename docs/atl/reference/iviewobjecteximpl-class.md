---
title: "IViewObjectExImpl Class | Microsoft Docs"
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
  - "ATL::IViewObjectExImpl<T>"
  - "ATL.IViewObjectExImpl"
  - "ATL::IViewObjectExImpl"
  - "ATL.IViewObjectExImpl<T>"
  - "IViewObjectExImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], рисование"
  - "advise sinks"
  - "IViewObjectEx ATL implementation"
  - "IViewObjectExImpl class"
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IViewObjectExImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и предоставляет по умолчанию реализации интерфейсов [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) и [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IViewObjectExImpl :  
public IViewObjectEx  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IViewObjectExImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IViewObjectExImpl::Draw](../Topic/IViewObjectExImpl::Draw.md)|Рисует представление элемента управления на контекст устройства.|  
|[IViewObjectExImpl::Freeze](../Topic/IViewObjectExImpl::Freeze.md)|Заморозит отображаемый представление элемента управления, чтобы оно не изменяется до `Unfreeze`.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](../Topic/IViewObjectExImpl::GetAdvise.md)|Извлекает существующее вспомогательное соединение приемников на элементе управления, если он имеется.|  
|[IViewObjectExImpl::GetColorSet](../Topic/IViewObjectExImpl::GetColorSet.md)|Возвращает логическое палитру, используемую элементом управления для рисования.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](../Topic/IViewObjectExImpl::GetExtent.md)|Извлекает размер отображения элемента управления в единицах HIMETRIC \(0,01 миллиметрах на единицу\) из элемента данных [CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md) класса элемента управления.|  
|[IViewObjectExImpl::GetNaturalExtent](../Topic/IViewObjectExImpl::GetNaturalExtent.md)|Предоставляет подсказки для изменения размера, из контейнера для объекта для использования по мере того, как пользователь изменяет размер его.|  
|[IViewObjectExImpl::GetRect](../Topic/IViewObjectExImpl::GetRect.md)|Возвращает прямоугольник, описывающие аспект запрашиваемого документа.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](../Topic/IViewObjectExImpl::GetViewStatus.md)|Сведения о возвращений о прозрачности объекта и какие аспекты документа поддерживаются.|  
|[IViewObjectExImpl::QueryHitPoint](../Topic/IViewObjectExImpl::QueryHitPoint.md)|Проверяет, находится ли заданная точка в заданном прямоугольнике и возвращает значение [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) в `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](../Topic/IViewObjectExImpl::QueryHitRect.md)|Проверяет, перекрывается ли прямоугольник элемента управления любой точки в прямоугольнике указанного расположения и возвращает значение **HITRESULT**  в `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](../Topic/IViewObjectExImpl::SetAdvise.md)|Устанавливает связь между элементом управления и получатель advise поэтому получатель может уведомить об изменениях в представлении элемента управления.|  
|[IViewObjectExImpl::Unfreeze](../Topic/IViewObjectExImpl::Unfreeze.md)|Unfreezes отображаемый представление элемента управления.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Интерфейсы [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) и [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) позволяют элемент управления для отображения непосредственно, а также создания и управления приемник advise для уведомления контейнер изменений при отображении элемента управления.  Интерфейс **IViewObjectEx** обеспечивает поддержку расширенных функций элемента управления как документ фликер\- свободна, и прозрачные элементы управления, прямоугольные, а выполняемая строка\- тестирование \(например, как закрыть щелчка мыши должен быть должен считаться в элементе управления\).  Класс `IViewObjectExImpl` предоставляет реализацию по умолчанию для этих интерфейсов и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
## Иерархия наследования  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Учебник](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Class Overview](../../atl/atl-class-overview.md)