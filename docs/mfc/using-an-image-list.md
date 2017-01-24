---
title: "Использование списка изображений | Microsoft Docs"
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
  - "CImageList - класс, использование"
  - "списки изображений [C++]"
  - "списки [C++], изображение"
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование списка изображений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Типичное потребление списка изображений соответствующий шаблон ниже:  
  
-   Создает объект [CImageList](../Topic/CImageList%20Class.md) и вызовите одну из перегрузок своей функции [Создать](../Topic/CImageList::Create.md) для создания списка изображений и вложить его в объект `CImageList`.  
  
-   Если не был добавлен способ, при создании списка изображений можно добавлять изображения в список изображений, вызвав функцию\-член [Добавить](../Topic/CImageList::Add.md) или [Чтение](../Topic/CImageList::Read.md).  
  
-   Связывание списка изображений с элементом управления, вызывая соответствующую функцию\-член, элемента управления или рисунок отображает из списка изображений самостоятельно с помощью функции\-члена [Рисование](../Topic/CImageList::Draw.md) списка изображений.  
  
-   Можно разрешить пользователю для перетаскивания изображение, с помощью списка изображений встроенную поддержку для перетаскивания.  
  
> [!NOTE]
>  Если список изображений был создан с помощью оператора **новый**, необходимо удалить объект `CImageList` по завершении с ним.  
  
## См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)