---
title: "Ошибка компилятора C2492 | Microsoft Docs"
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
  - "C2492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2492"
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": данные "thread" не могут иметь интерфейс dll  
  
 Переменная объявлена с использованием атрибута [thread](../../cpp/thread.md) и интерфейса DLL.  Адрес переменной `thread` известен только во время выполнения, поэтому ее нельзя связать с импортом или экспортом DLL.  
  
 Следующий пример приводит к возникновению ошибки C2492:  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```