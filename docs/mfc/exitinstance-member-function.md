---
title: "Функция-член ExitInstance | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp::ExitInstance"
  - "CWinApp.ExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp - класс, ExitInstance"
  - "ExitInstance - метод"
  - "программы [C++], завершение"
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция-член ExitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Функцию\-член [ExitInstance](../Topic/CWinApp::ExitInstance.md) класса [CWinApp](../mfc/reference/cwinapp-class.md) вызывается каждый раз копию приложения завершена, обычно в результате прекращая пользователя приложения.  
  
 Переопределите `ExitInstance`, если необходима специальная очистка обработки, например высвобождение ресурсов \(GDI\) приборного интерфейса графических или отменить память, используемая во время выполнения программы.  Очистка стандартных элементов, такие как документы и представления, предоставленная платформой, с другими функциями переопределяемого метода для обеспечения специальных для очистки этих объектов.  
  
## См. также  
 [CWinApp: класс приложений](../Topic/CWinApp:%20The%20Application%20Class.md)