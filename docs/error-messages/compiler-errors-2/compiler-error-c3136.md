---
title: "Ошибка компилятора C3136 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3136"
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3136
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"интерфейс" : интерфейс COM может наследовать только от другого интерфейса COM; "интерфейс" не является интерфейсом COM  
  
 Интерфейс, к которому был применен [атрибут интерфейса](../../windows/interface-attributes.md), наследует от интерфейса, не являющегося интерфейсом COM.  Интерфейс COM должен в конечном итоге наследовать от интерфейса `IUnknown`.  Любой интерфейс, перед которым стоит атрибут интерфейса, считается интерфейсом COM.  
  
 Следующий пример приводит к возникновению ошибки C3136:  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```