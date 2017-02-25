---
title: "Предупреждение компилятора (уровень 1) C4103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4103"
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имяфайла" : выравнивание изменено после включения заголовка, возможно, пропущена прагма\-директива \#pragma pack\(pop\)  
  
 Упаковка влияет на структуру классов в памяти, и если способ упаковки меняется от одного файла заголовка к другому, могут возникать проблемы.  
  
 Чтобы устранить это предупреждение, следует использовать прагма\-директиву \#pragma [pack](../../preprocessor/pack.md)\(pop\) перед выходом из файла заголовка.  
  
 Следующий пример приводит к возникновению ошибки C4103:  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 И далее,  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```