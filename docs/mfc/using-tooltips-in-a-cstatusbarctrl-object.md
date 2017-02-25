---
title: "Использование всплывающих подсказок в объекте CStatusBarCtrl | Microsoft Docs"
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
  - "CStatusBarCtrl - класс, всплывающие подсказки"
  - "строки состояния, всплывающие подсказки"
  - "всплывающие подсказки [C++], использование в строках состояния"
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Использование всплывающих подсказок в объекте CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Чтобы включить подсказки для элемента управления в строке состояния, создайте объект `CStatusBarCtrl` со стилем **SBT\_TOOLTIPS**.  
  
> [!NOTE]
>  Если используется объект `CStatusBar` для реализации строки состояния, используйте функции `CStatusBar::CreateEx`.  Это позволяет определить дополнительные стили для внутреннего объекта **CStatusBarCtrl** .  
  
 После создания объекта `CStatusBarCtrl` успешно создан, используйте [CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md) и [CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md) для установки и извлечения текст TIP для определенной области.  
  
 После того как всплывающая подсказка задана отображается, только если часть не содержит Значок и текст не существует, или если весь текст не удается отобразить внутри тела.  Всплывающие подсказки не поддерживаются в простом режиме.  
  
## См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)