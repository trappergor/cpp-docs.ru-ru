---
title: "Сведения об изображениях в списках изображений | Microsoft Docs"
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
  - "CImageList - класс, сведения об изображении в"
  - "списки изображений [C++], сведения об изображении в"
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Сведения об изображениях в списках изображений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../Topic/CImageList%20Class.md) содержит несколько функций, которые извлекают данные из списка изображений.  Функцию\-член [GetImageInfo](../Topic/CImageList::GetImageInfo.md) заполняет структуру `IMAGEINFO` информацией об одном образе, включая дескрипторы растровых изображений образа и маски, числа и самолетов бит на пиксель цвета и ограничивающего прямоугольника образа в растровое изображение образа.  Эти сведения можно использовать для непосредственного управления растровые изображения для образа.  
  
 Функцию\-член [GetImageCount](../Topic/CImageList::GetImageCount.md) извлекает число изображений в списке изображений.  
  
 Можно создать Значок на основе способом и маску в списке изображений с помощью функции\-члена [ExtractIcon](../Topic/CImageList::ExtractIcon.md).  Функция возвращает дескриптор нового Значка.  
  
## См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)