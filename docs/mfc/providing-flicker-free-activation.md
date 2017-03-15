---
title: "Предоставление активации без мерцания | Microsoft Docs"
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
  - "активация [C++], без мерцания"
  - "мерцание, MFC ActiveX - элементы управления"
  - "элементы управления MFC ActiveX [C++], без мерцания"
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Предоставление активации без мерцания
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если элемент управления рисует идентично в неактивном и активных состояниях \(и не использует безоконную активацию\), можно исключить операции рисования и соответствующей мерцание визуальных, которые обычно выполняются занимает переход между состояниями неактивным и активными.  Для этого включает флажок **noFlickerActivate** в наборе флажков, возвращенных методом [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Примеры.  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/CPP/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-flicker-free-activation_3.cpp)]  
  
 Код, чтобы включить этот флажок создается автоматически, если выбирать параметр **Свободная от Мерцание активация** на странице [Параметры элементов управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) создает элемент управления с помощью мастера элементов управления ActiveX MFC.  
  
 При использовании безоконную активацию, эта оптимизация не влияет.  
  
## См. также  
 [Элементы управления ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)