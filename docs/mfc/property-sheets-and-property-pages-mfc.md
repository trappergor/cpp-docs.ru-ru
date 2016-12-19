---
title: "Вкладки свойств и страницы свойств (MFC) | Microsoft Docs"
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
  - "CPropertyPage - класс, вкладки свойств и страницы"
  - "CPropertySheet - класс, вкладки свойств и страницы"
  - "диалоговые окна MFC, вкладки"
  - "страницы свойств, страницы свойств"
  - "страницы свойств, страницы свойств"
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Вкладки свойств и страницы свойств (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC [диалоговое окно](../mfc/dialog-boxes.md) может принимать на вкладке «диалоговое окно» обзор, включив страниц свойств.  Вызов «страницы свойств» в MFC, данного типа диалогового окна, аналогично различные диалоговые окна в Microsoft Word, Excel и о том, что содержит Visual C\+\+, стек предварительного таблиц, подобно стека папок, из файла увиденные перед подперло, или группу в составе каскадированные окна.  Элементы управления на передней вкладке отображаются; только на вкладку с надписью обратных вызовов отображается на вкладках.  Страницы свойств особенно полезны для управления большими объемами свойства или параметров, которые являются частью достаточно аккуратно в несколько групп.  Как правило, одна страница свойств может упростить интерфейс пользователя, заменив несколько отдельных диалоговых окон.  
  
 Начиная с версии MFC 4.0, страниц свойств реализуются с помощью общие элементы управления, с версией 3.51 Windows 95 и Windows NT и далее.  
  
 Страницы свойств реализуются классы [CPropertySheet](../mfc/reference/cpropertysheet-class.md) и [CPropertyPage](../mfc/reference/cpropertypage-class.md) \(преобразований в справочнике по MFC\).  `CPropertySheet` определяет общее диалоговое окно, которое может содержать несколько «страницы» на основе `CPropertyPage`.  
  
 Сведения о создании и работе с помощью страниц свойств см. в разделе [Вкладки свойств](../mfc/property-sheets-mfc.md).  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Вкладки свойств и страницы свойств в MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Обмен данными](../mfc/exchanging-data.md)   
 [Создание безмодальной вкладки свойства](../mfc/creating-a-modeless-property-sheet.md)   
 [Обработка кнопки "Применить"](../mfc/handling-the-apply-button.md)