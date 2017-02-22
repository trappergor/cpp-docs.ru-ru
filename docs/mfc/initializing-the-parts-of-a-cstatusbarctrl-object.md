---
title: "Инициализация частей объекта CStatusBarCtrl | Microsoft Docs"
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
  - "CStatusBarCtrl - класс, объявление частей"
  - "CStatusBarCtrl - класс, простой режим"
  - "значки, использование в строках состояния"
  - "простые строки состояния"
  - "строки состояния, объявление частей"
  - "строки состояния, значки"
  - "строки состояния, простой режим"
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Инициализация частей объекта CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

По умолчанию в строке состояния отображается сведения о состоянии с помощью отдельные области.  Эти области \(также двух частей\) могут содержать или текстовую строку, Значок, или оба.  
  
 Используйте [SetParts](../Topic/CStatusBarCtrl::SetParts.md), чтобы определить количество частей и длину, строка будет иметь состояния.  После создания части строки состояния, вызывать для [SetText](../Topic/CStatusBarCtrl::SetText.md) и [SetIcon](../Topic/CStatusBarCtrl::SetIcon.md), чтобы задать текст или Значок для определенной части строки состояния.  Как только часть успешно была установлена, элемент управления автоматически перерисовке.  
  
 Следующий пример инициализирует существующий объект `CStatusBarCtrl` \(`m_StatusBarCtrl`\) с 4 областями и затем значку \(IDI\_ICON1\) и текст во второй части.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/CPP/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 Дополнительные сведения о параметре режим объекта `CStatusBarCtrl` простому см. в разделе [Устанавливать режим объекта CStatusBarCtrl](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)