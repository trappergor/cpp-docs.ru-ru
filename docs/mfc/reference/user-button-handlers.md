---
title: "Обработчики пользовательских кнопок | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_BN_HILITE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_CLICKED"
  - "ON_BN_PAINT"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_BN_CLICKED"
  - "ON_BN_DISABLE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_HILITE"
  - "ON_BN_PAINT"
  - "ON_BN_UNHILITE"
  - "пользовательские кнопки"
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Обработчики пользовательских кнопок
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления соответствуют прототипам функции.  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_BN\_CLICKED \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_BN\_DISABLE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_BN\_DOUBLECLICKED \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_BN\_HILITE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_BN\_PAINT \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
|ON\_BN\_UNHILITE \( \<id\>, \<memberFxn\> \)|memberFxn afx\_msg новое \(\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)