---
title: "CMFCRibbonSlider Class | Microsoft Docs"
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
  - "CMFCRibbonSlider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSlider class"
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSlider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonSlider` реализующий элемент управления "ползунок", можно добавить в область ленты или строке состояния ленты.  Элемент управления "ползунок" ленты напоминает ползунков масштаба, которые появляются в приложения office 2007.  
  
## Синтаксис  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](../Topic/CMFCRibbonSlider::CMFCRibbonSlider.md)|Конструкции и инициализируют элемент управления "ползунок" ленты.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonSlider::GetPos](../Topic/CMFCRibbonSlider::GetPos.md)|Возвращает текущую позицию управления "ползунок".|  
|[CMFCRibbonSlider::GetRangeMax](../Topic/CMFCRibbonSlider::GetRangeMax.md)|Возвращает максимальное значение "ползунок".|  
|[CMFCRibbonSlider::GetRangeMin](../Topic/CMFCRibbonSlider::GetRangeMin.md)|Возвращает минимальное значение "ползунок".|  
|[CMFCRibbonSlider::GetRegularSize](../Topic/CMFCRibbonSlider::GetRegularSize.md)|Возвращает обычный размер элемента ленты.  \(Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)\).|  
|[CMFCRibbonSlider::GetZoomIncrement](../Topic/CMFCRibbonSlider::GetZoomIncrement.md)|Возвращает размер увеличения масштаба для управления "ползунок".|  
|[CMFCRibbonSlider::HasZoomButtons](../Topic/CMFCRibbonSlider::HasZoomButtons.md)|Указывает, имеет ли ползунок кнопок масштабирования.|  
|[CMFCRibbonSlider::OnDraw](../Topic/CMFCRibbonSlider::OnDraw.md)|Вызываемый платформой для рисования элемента ленты.  \(Переопределяет [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)\).|  
|[CMFCRibbonSlider::SetPos](../Topic/CMFCRibbonSlider::SetPos.md)|Задает текущую позицию управления "ползунок".|  
|[CMFCRibbonSlider::SetRange](../Topic/CMFCRibbonSlider::SetRange.md)|Определяет диапазон управления "ползунок" с помощью минимального и максимального значений.|  
|[CMFCRibbonSlider::SetZoomButtons](../Topic/CMFCRibbonSlider::SetZoomButtons.md)|Показать или скрывает кнопки увеличения.|  
|[CMFCRibbonSlider::SetZoomIncrement](../Topic/CMFCRibbonSlider::SetZoomIncrement.md)|Размер наборов увеличения масштаба для управления "ползунок".|  
  
## Заметки  
 Можно использовать метод `SetRange` чтобы настроить диапазон масштабирования для инкрементов ползунка.  Можно задать текущее положение ползунка с помощью метода `SetPos`.  
  
 Можно отобразить круговые кнопок масштабирования слева и справа управления "ползунок" с помощью метода `SetZoomButtons`.  По умолчанию ползунок масштаба горизонтально кнопку левой указывает знак "Минус" и правая кнопка " увеличить " отображается знак "плюс".  
  
 Метод `SetZoomIncrement` определяет шаг приращения для добавления или вычитания из текущего положения, когда пользователь нажимает кнопки увеличения.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCRibbonSlider` для задания свойств ползунка.  Примере показано создание объекта `CMFCRibbonSlider`, масштаба отображения кнопки присвойте текущая позиция управления "ползунок" и укажите диапазон значений для управления "ползунок".  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/CPP/cmfcribbonslider-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## Требования  
 **заголовок:** afxribbonslider.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)