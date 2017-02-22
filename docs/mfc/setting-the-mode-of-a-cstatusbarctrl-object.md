---
title: "Установка режима объекта CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl - класс, простые и непростые режимы"
  - "IsSimple - метод, использование"
  - "непростой режим и элементы управления строки состояния"
  - "SetSimple - метод"
  - "простой режим и элементы управления строки состояния"
  - "элементы управления строкой состояния, простые и непростые режимы"
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Установка режима объекта CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 Режима для объекта `CStatusBarCtrl` : простой и nonsimple.  В большинстве случаев, элемент управления " Строка состояния будет иметь один или несколько частей вместе с текстом и Значком возможно или Значками.  Это называется режимом nonsimple.  Дополнительные сведения об этом режиме см. в разделе [Инициализация части объекта CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Однако в некоторых случаях необходимо только для отображения линии отдельную текста.  В этом случае простой режим достаточно для себя.  Чтобы изменить режим объекта `CStatusBarCtrl` простому, вызывать в функцию\-член [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  После того как элемент управления " Строка состояния в простом режиме, установите текст, вызвав функцию\-член **SetText**, передавая 255 в качестве значения параметра **nPane**.  
  
 Можно использовать функцию [IsSimple](../Topic/CStatusBarCtrl::IsSimple.md), чтобы определить объект `CStatusBarCtrl` в каком режиме.  
  
> [!NOTE]
>  Если объект строки состояния изменения из nonsimple простому, или наоборот, окно немедленно перерисовать и, если применимо, все определенные части автоматически будут восстановлены.  
  
## См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)