---
title: "Предупреждение компилятора (уровень&#160;4) C4682 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4682"
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;4) C4682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"параметр": не указан атрибут параметра направления, по умолчанию принимается \[in\]  
  
 Метод параметра в интерфейсе с атрибутами не содержит атрибута направления [in](../Topic/in%20\(C++\).md) или [out](../Topic/out%20\(C++\).md). По умолчанию принимается атрибут in.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
 Следующий пример приводит к возникновению предупреждения C4682:  
  
```  
// C4682.cpp // compile with: /W4 #pragma warning(default : 4682) #include <windows.h> [module(name="MyModule")]; [ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ] __interface IMyIface : IUnknown { HRESULT f1(int i, int *pi); // C4682 // try the following line // HRESULT f1([in] int i, [in] int *pi); }; int main() { }  
```