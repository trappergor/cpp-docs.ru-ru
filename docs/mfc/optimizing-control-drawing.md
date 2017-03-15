---
title: "Оптимизация рисования элементов управления | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX - элементы управления, оптимизация"
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Оптимизация рисования элементов управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если элемент управления проинструктирован для рисования в контейнер\- предоставленный контекст устройства, обычно это выделяет объекты GDI \(например, перья, кисти и шрифты\) в контексте устройства, выполняет свои операции рисования, и восстановление предыдущие объекты GDI.  Если контейнер имеет несколько элементов управления, которые должны быть выписанным в одном и том же контексте устройства, каждый элемент управления выделяет объекты, GDI он требует времени, можно сохранить отдельно, если элементы управления не восстановление ранее выбранные объекты.  Наконец, контейнер элементов управления вычерченны могут автоматически восстановить исходные объекты.  
  
 Чтобы определить, поддерживает ли контейнер этот метод, элемент управления может вызывать функцию\-член [COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md).  Если эта функция возвращает значение **TRUE**, то элемент управления может пропустить шаг обычно восстановление ранее выбранные объекты.  
  
 Рассмотрим элемент управления, который имеет следующую \(неоптимизированную\) функции `OnDraw`:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/CPP/optimizing-control-drawing_1.cpp)]  
  
 Перо и кисти в этом примере локальные переменные, это означает, что они будут деструкторы вызываются, когда они находятся вне области \(если функция `OnDraw` завершение\).  Деструкторы попытаются удаление соответствующие объекты GDI.  Однако они не должны быть удалены, если планируется оставить их выбранный в контексте устройства после возврата из `OnDraw`.  
  
 Чтобы предотвратить объекты [CPen](../Topic/CPen%20Class.md) и [CBrush](../mfc/reference/cbrush-class.md) из уничтожить при `OnDraw` завершается, сохраните их в переменных\-членах вместо локальных переменных.  В объявлении класса элемента управления добавьте объявления для 2 новых переменных\-членов:  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/CPP/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/CPP/optimizing-control-drawing_3.h)]  
  
 Затем, при `OnDraw` можно переписать следующим образом:  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/CPP/optimizing-control-drawing_4.cpp)]  
  
 Такой подход позволяет избежать создания пера и кисти каждый раз `OnDraw` данной функции.  Улучшение скорости поступает за счет обслуживания дополнительных данных экземпляра.  
  
 Если изменения свойств ForeColor или BackColor, перо или кисть должен быть создан повторно.  Чтобы сделать это, переопределяет функции\-члены [OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md) и [OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md).  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/CPP/optimizing-control-drawing_5.cpp)]  
  
 Наконец, исключить ненужные вызовы `SelectObject` измените `OnDraw` следующим образом:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/CPP/optimizing-control-drawing_6.cpp)]  
  
## См. также  
 [Элементы управления ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)   
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [мастер элементов управления MFC ActiveX](../mfc/reference/mfc-activex-control-wizard.md)   
 [Элементы управления ActiveX в MFC. Закраска элементов управления ActiveX](../mfc/mfc-activex-controls-painting-an-activex-control.md)