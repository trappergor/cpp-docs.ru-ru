---
title: "Свойство &quot;Модификатор&quot; сочетания клавиш | Microsoft Docs"
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
  - "Modifier - свойство"
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Свойство &quot;Модификатор&quot; сочетания клавиш
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ниже приведены допустимые значения свойства "Модификатор" для таблицы сочетаний клавиш.  
  
|Значение|Описание|  
|--------------|--------------|  
|**None**|Пользователь нажимает только одну клавишу.  Этот вариант лучше всего подходит для значений ASCII\/ANSI в диапазоне от 001 до 026, которые интерпретируются как сочетания от ^A до ^Z \(от CTRL\-A до CTRL\-Z\).|  
|**Alt**|Пользователь должен прижать клавишу ALT, прежде чем нажать другую клавишу.|  
|**CTRL**|Пользователь должен нажать клавишу CTRL, прежде чем нажать другую клавишу.  Нельзя использовать для значений типа ASCII.|  
|**Сдвиг**|Пользователь должен прижать клавишу SHIFT, прежде чем нажать другую клавишу.|  
|**CTRL\+ALT**|Пользователь должен прижать клавиши ALT и CTRL, прежде чем нажать другую клавишу.  Нельзя использовать для значений типа ASCII.|  
|**CTRL\+SHIFT**|Пользователь должен прижать клавиши CTRL и SHIFT, прежде чем нажать другую клавишу.  Нельзя использовать для значений типа ASCII.|  
|**ALT\+SHIFT**|Пользователь должен прижать клавиши ALT и SHIFT, прежде чем нажать другую клавишу.  Нельзя использовать для значений типа ASCII.|  
|**CTRL\+ALT\+SHIFT**|Пользователь должен прижать клавиши ALT, CTRL и SHIFT, прежде чем нажать другую клавишу.  Нельзя использовать для значений типа ASCII.|  
  
## Требования  
 Win32  
  
## См. также  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)