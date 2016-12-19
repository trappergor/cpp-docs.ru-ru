---
title: "Функции обмена данными диалоговых окон для элементов управления OLE | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обмен данными диалоговых окон (DDX), поддержка OLE"
  - "элементы управления OLE, функции DDX"
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функции обмена данными диалоговых окон для элементов управления OLE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе перечислены функции DDX\_OC, используемые для обмена данными между свойством элемента управления OLE в диалоговом окне, представлением формы или элемента управления объектом и элементом данных диалогового окна, представления объекта формы или элемента управления.  
  
### Функции DDX\_OC  
  
|||  
|-|-|  
|[DDX\_OCBool](../Topic/DDX_OCBool.md)|Элемент управления передачей данных между свойством **bool** элемента управления OLE и элементом данных **bool**.|  
|[DDX\_OCBoolRO](../Topic/DDX_OCBoolRO.md)|Элемент управления передачей данных между **bool** только для чтения свойство элемента управления OLE и элементом данных **bool**.|  
|[DDX\_OCColor](../Topic/DDX_OCColor.md)|Элемент управления передачей данных между свойством **OLE\_COLOR** элемента управления OLE и элементом данных **OLE\_COLOR**.|  
|[DDX\_OCColorRO](../Topic/DDX_OCColorRO.md)|Элемент управления передачей данных между **OLE\_COLOR** только для чтения свойство элемента управления OLE и элементом данных **OLE\_COLOR**.|  
|[DDX\_OCFloat](../Topic/DDX_OCFloat.md)|Управление передачи данных по **плавающее** \(или **double**\) между свойством элемента управления OLE и элементом данных **плавающее** \(или **double**\).|  
|[DDX\_OCFloatRO](../Topic/DDX_OCFloatRO.md)|Управление передачи данных по **плавающее** \(или **double**\) между только для чтения свойство элемента управления OLE и элементом данных **плавающее** \(или **double**\).|  
|[DDX\_OCInt](../Topic/DDX_OCInt.md)|Управление передачи данных по `int` \(или **long**\) между свойством элемента управления OLE и элементом данных `int` \(или **long**\).|  
|[DDX\_OCIntRO](../Topic/DDX_OCIntRO.md)|Управление передачи данных по `int` \(или **long**\) между только для чтения свойство элемента управления OLE и элементом данных `int` \(или **long**\).|  
|[DDX\_OCShort](../Topic/DDX_OCShort.md)|Элемент управления передачей данных между свойством **short** элемента управления OLE и элементом данных **short**.|  
|[DDX\_OCShortRO](../Topic/DDX_OCShortRO.md)|Элемент управления передачей данных между **short** только для чтения свойство элемента управления OLE и элементом данных **short**.|  
|[DDX\_OCText](../Topic/DDX_OCText.md)|Элемент управления передачей данных между свойством **CString**  элемента управления OLE и элементом данных **CString** .|  
|[DDX\_OCTextRO](../Topic/DDX_OCTextRO.md)|Элемент управления передачей данных между **CString**  только для чтения свойство элемента управления OLE и элементом данных **CString** .|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)