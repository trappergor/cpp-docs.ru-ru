---
title: "Добавление элементов управления на вкладку свойств | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [MFC], добавление к вкладкам свойств"
  - "страницы свойств, добавление элементов управления"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление элементов управления на вкладку свойств
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

По умолчанию страница свойств выделяет область окна для страниц свойств, индекса вкладок и ОК, Отмены и применяет кнопки. Страница свойств \(a безрежимная не имеет ОК, не отменить и нельзя применить кнопки\). Можно добавить другие элементы управления на страницу свойств.  Например, можно добавить в окне просмотра справа от области страницы свойств для отображения пользователю, что текущие параметры выглядит какTfи, если применяется к внешнему объекту.  
  
 Можно добавить элементы управления в диалоговое окно страницы свойств в обработчике `OnCreate`.  Accommodating дополнительные элементы управления обычно требуется развернуть размер диалогового окна " страницы свойств ".  После вызова базового класса **CPropertySheet::OnCreate** необходимо вызвать метод [GetWindowRect](../Topic/CWnd::GetWindowRect.md) для получения ширину и высоту выбранного окна " страницы свойств ", разверните измерения прямоугольника, и вызывает метод [MoveWindow](../Topic/CWnd::MoveWindow.md) для изменения размера окна страницы свойств.  
  
## См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)   
 [CPropertyPage Class](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Class](../mfc/reference/cpropertysheet-class.md)