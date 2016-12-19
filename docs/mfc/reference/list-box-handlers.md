---
title: "Обработчики списков | Microsoft Docs"
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
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_SETFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_KILLFOCUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "списки, обработчики списков"
  - "ON_LBN_DBLCLK"
  - "ON_LBN_ERRSPACE"
  - "ON_LBN_KILLFOCUS"
  - "ON_LBN_SELCHANGE"
  - "ON_LBN_SETFOCUS"
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработчики списков
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления имеют соответствующие прототип функции.  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_LBN\_DBLCLK \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_LBN\_ERRSPACE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_LBN\_KILLFOCUS \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_LBN\_SELCHANGE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_LBN\_SETFOCUS \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)