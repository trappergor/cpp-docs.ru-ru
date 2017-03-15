---
title: "When Do I Need to Call AtlAxWinTerm? | Microsoft Docs"
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
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm method"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 12
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinTerm?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отменяет регистрацию [AtlAxWinTerm](../Topic/AtlAxWinTerm.md) класс окна **"AtlAxWin80"**.  Необходимо вызывать эту функцию \(если они более не нужны для создания окна узла\), то после того, как были уничтожены все существующие окна основного приложения.  Если эта функция вызывается, то класс окна будет автоматически при регистрации процесс завершается.  
  
## См. также  
 [When Do I Need to Call AtlAxWinInit?](../atl/when-do-i-need-to-call-atlaxwininit-q.md)   
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)