---
title: "CScrollView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CScrollView class"
  - "scrolling views"
  - "представления, прокрутка"
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CScrollView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CView](../Topic/CView%20Class.md) с возможностями прокрутки.  
  
## Синтаксис  
  
```  
class CScrollView : public CView  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CScrollView::CScrollView](../Topic/CScrollView::CScrollView.md)|Создает объект `CScrollView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CScrollView::CheckScrollBars](../Topic/CScrollView::CheckScrollBars.md)|Указывает, имеет ли представление прокрутки по горизонтали и вертикальные полосы прокрутки.|  
|[CScrollView::FillOutsideRect](../Topic/CScrollView::FillOutsideRect.md)|Заполняет область представления ожидания при необходимости выполняя прокрутку области.|  
|[CScrollView::GetDeviceScrollPosition](../Topic/CScrollView::GetDeviceScrollPosition.md)|Возвращает текущую позицию прокрутки в единицах устройства.|  
|[CScrollView::GetDeviceScrollSizes](../Topic/CScrollView::GetDeviceScrollSizes.md)|Возвращает текущий режим сопоставления полный размер и линию и размеры страницы прокручиваемые представления.  Размер в единицах устройства.|  
|[CScrollView::GetScrollPosition](../Topic/CScrollView::GetScrollPosition.md)|Возвращает текущую позицию прокрутки в логических единицах.|  
|[CScrollView::GetTotalSize](../Topic/CScrollView::GetTotalSize.md)|Получает общий размер представления прокрутки в логических единицах.|  
|[CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)|Приводит к тому, что размер представления продиктовать размер своего кадра.|  
|[CScrollView::ScrollToPosition](../Topic/CScrollView::ScrollToPosition.md)|Прокручивает представление на заданный момент, указанный в логических единицах.|  
|[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)|Переводит представление прокрутки в режим шкала\-к\- соответствия.|  
|[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)|Устанавливает режим сопоставления представления прокрутки, полный размер, а горизонтальная и вертикальная прокрутка составляющих.|  
  
## Заметки  
 Самостоятельно обрабатывать стандартный прокрутку в любом классе, производном от `CView` путем переопределения сообщение\- функции\-члены [OnHScroll](../Topic/CWnd::OnHScroll.md) и сопоставленные [OnVScroll](../Topic/CWnd::OnVScroll.md).  Но `CScrollView` добавляет следующие функции к его возможностей `CView`:  
  
-   Он управляет размерами окна и окна просмотра и режимы сопоставления.  
  
-   Оно автоматически перемещается в ответ на сообщения полосы прокрутки.  
  
-   Оно автоматически перемещается в ответ на сообщения от клавиатуры, отличных от прокрутки или колесика мыши, IntelliMouse.  
  
 Автоматическая прокрутка в ответ на сообщения от клавиатуры, добавить сообщение WM\_KEYDOWN и тест для VK\_DOWN, VK\_PREV и вызова [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Самостоятельно обрабатывать прокрутку колесика мыши путем переопределения сообщение\- функции\-члены [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) и сопоставленные [OnRegisteredMouseWheel](../Topic/CWnd::OnRegisteredMouseWheel.md).  По мере того, как они поддерживают такие функции\-члены для `CScrollView`, предлагаемая расширение функциональности для [WM\_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617) сообщение поворота колесика.  
  
 Чтобы воспользоваться преимуществами автоматической прокрутки, наследуйте класс от `CScrollView` представления, а не из `CView`.  Если представление сначала создано, если нужно вычислить размер прокручиваемой представления, основываясь на размер документа, вызовите функцию\-член `SetScrollSizes` из переопределения или [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) или [CView::OnUpdate](../Topic/CView::OnUpdate.md).  \(Необходимо написать собственный код для запроса размер документа.  Пример см. в разделе [Образец Scribble](../../top/visual-cpp-samples.md)\).  
  
 Вызов к функции\-члену `SetScrollSizes` задает режим сопоставления представления всего измерения представления прокрутки и количество для прокрутки по горизонтали и по вертикали.  Все размеры в логических единицах.  Логический размер представления обычно вычисляется на основе данных, хранящихся в документе, но в некоторых случаях может потребоваться указать фиксированный размер.  Примеры обоих подходов см. в разделе [CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md).  
  
 Указать число для прокрутки по горизонтали и вертикали в логических единицах.  По умолчанию если пользователь щелкает base "полоса прокрутки" вне ползунка полосы прокрутки, `CScrollView` прокручивает "страница". Если пользователь нажимает кнопку прокрутки на любом элементе полосы прокрутки, `CScrollView` прокручивает "линия". По умолчанию страница 1\/10 из полного размера представления; линия 1\/10 из размера страницы.  Переопределите эти значения по умолчанию, передав пользовательские размеры в функции\-члене `SetScrollSizes`.  Например, можно установить размер по горизонтали в некоторой части полного размера, ширины размера и вертикальной линии в текущем высоте шрифта.  
  
 Вместо прокрутки, `CScrollView` может автоматически масштабирование представления с текущим размером окна.  В этом режиме представление не содержит полосы прокрутки и логическое представление растянуто или сжато приспособления к получению для клиентской области окна.  Использовать эту возможность шкала\-к\- соответствия, вызов [CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md).  \(Или `SetScaleToFitSize` или вызовите `SetScrollSizes`, но не оба\).  
  
 Прежде чем вызывать функцию\-член `OnDraw` пользовательского производного класса представления `CScrollView` автоматически обрабатывает начало координат окна просмотра для объекта устройство\- контекста `CPaintDC`, он передает в `OnDraw`.  
  
 Для обработки начало координат окна просмотра для окна прокрутки, `CScrollView` переопределяет [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md).  Эта корректировка автоматическая для контекста устройства `CPaintDC`, `CScrollView` передает в `OnDraw`, но ее следует вызывать **CScrollView::OnPrepareDC** для всех других контекстов устройства использовании, как `CClientDC`.  Можно переопределить **CScrollView::OnPrepareDC** для задания пера, цвет фона и другие атрибуты документа, но вызвать базовый класс, чтобы выполнить масштабирование.  
  
 Полосы прокрутки могут появляться в 3 размещения по отношению к представлению, как показано в следующих случаях:  
  
-   Стандартные полосы прокрутки окно\- стиля можно задать для представления с помощью **WS\_HSCROLL** и **WS\_VSCROLL**[стили Windows](../Topic/Window%20Styles.md).  
  
-   Элементы управления "полоса прокрутки" можно также добавлять к кадру, содержащий представление, в этом случае платформа переадресует `WM_HSCROLL` и сообщения от `WM_VSCROLL` фреймового окна на активное в данный момент представление.  
  
-   Платформа также переадресуют сообщения прокрутки элемента управления разделителем `CSplitterWnd` для текущего активного панели splitter \(представление\).  Установленный в [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) с общих полосами прокрутки, объект `CScrollView` будет использовать общие один вместо создания его.  
  
 Дополнительные сведения об использовании `CScrollView` см. в разделе [Архитектура документов и представлений](../Topic/Document-View%20Architecture.md) и [Производный представление классифицирует доступный в MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 `CScrollView`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC просматривает DIBLOOK](../../top/visual-cpp-samples.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)