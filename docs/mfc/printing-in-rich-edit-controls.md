---
title: "Печать в элементах управления &quot;Rich Edit&quot; | Microsoft Docs"
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
  - "CRichEditCtrl - класс, печать"
  - "печать [MFC], CRichEditCtrl"
  - "элементы управления Rich Edit, печать"
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Печать в элементах управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это свойство указывает, что элемент управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) отображает выходные данные для конкретного устройства, например принтера.  Можно также указать устройство вывода, для которого форматы управления расширенного редактирования его текст.  
  
 Для форматирования часть содержимого управления расширенного редактирования для конкретного устройства можно использовать функцию\-член [FormatRange](../Topic/CRichEditCtrl::FormatRange.md).  Структура [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911), используемую с данной функцией определяет диапазон текста для форматирования, так и контекст устройства \(DC\) для целевого устройства.  
  
 После форматирования текста для устройства вывода, можно отправить вывод в устройства с помощью функции\-члена [DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md).  Повторное использование `FormatRange` и `DisplayBand`, приложение, которое выводит содержимого элемента управления расширенного редактирования может реализовать использование диапазонов. \(Использование диапазонов деление вывода на более мелкие части для распечатки\).  
  
 Можно использовать функцию\-член [SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md), чтобы определить целевое устройство, для которого форматы управления расширенного редактирования его текст.  Эта функция полезна для режима представления WYSIWYG \(что будет видно, что при получении\) форматирования текста, в котором апликаций позиции с помощью метрика шрифта установленного по умолчанию вместо экрана.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)