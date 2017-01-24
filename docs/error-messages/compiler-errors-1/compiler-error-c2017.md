---
title: "Ошибка компилятора C2017 | Microsoft Docs"
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
  - "C2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2017"
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимая управляющая последовательность  
  
 Управляющая последовательность, такая как \\t, появляется вне знака или константы строки.  
  
 Следующий пример приводит к возникновению ошибки C2017:  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 Ошибка С2017 может возникнуть, если строчный оператор используется со строками, которые включают управляющую последовательность.  
  
 Следующий пример приводит к возникновению ошибки C2017:  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```