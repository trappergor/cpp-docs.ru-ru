---
title: "Перекрытия изображений в списках изображений | Microsoft Docs"
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
  - "CImageList - класс, перекрытия изображений в"
  - "списки изображений [C++], перекрытия изображений в"
  - "перекрытия"
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Перекрытия изображений в списках изображений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждый список изображений \([CImageList](../Topic/CImageList%20Class.md)\) содержит список изображений для использования в качестве маски перекрытия.  «Маска перекрытия» образ рисование прозрачно над другими способами.  Любой изображение можно использовать в качестве маски перекрытия.  Можно указать до 4 накладываться на маски в списке изображений.  
  
 Добавляется индекс образа в список масок перекрытия с помощью функции\-члена [SetOverlayImage](../Topic/CImageList::SetOverlayImage.md), индекс изображения и индекс перекрытия маски.  Обратите внимание, что индексы для перекрытия маски единицы, а не с индексацией от нуля.  
  
 Изображается перекрытия маски над образом, используя один вызов **Рисование**.  В число этих параметров входят индекс изображения для рисования и индекс перекрытия маски.  Необходимо использовать макрос [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408), чтобы определить индекс перекрытия маски.  Можно также определить образ перекрытия при вызове функции\-члена [DrawIndirect](../Topic/CImageList::DrawIndirect.md).  
  
## См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)