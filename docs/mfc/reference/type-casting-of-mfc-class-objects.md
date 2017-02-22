---
title: "Приведение типов объектов классов MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы приведения"
  - "макросы, приведение указателей"
  - "макросы, приведение типов"
  - "указатели, приведение типов"
  - "приведения типа"
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Приведение типов объектов классов MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Макросы приведения типов предоставляют способ приведение заданный указатель на указатель, который указывает на объект определенного класса с или без проверки, поскольку приведение.  
  
 В следующей таблице перечислены макросы приведения типов MFC.  
  
### Макросы, возникающие указателей на объекты классов MFC  
  
|||  
|-|-|  
|[DYNAMIC\_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|Возвращает указатель на указатель на объект класса во время проверки, чтобы определить, поскольку приведение.|  
|[STATIC\_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|Возвращает указатель на объект из одного класса к указателю связанного типа.  В отладочном построении причины **ASSERT**, если объект не является «типа» тип целевого объекта.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)