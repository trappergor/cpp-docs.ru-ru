---
title: "Ошибка компилятора C3638 | Microsoft Docs"
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
  - "C3638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3638"
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": стандартные операторы преобразования упаковки и распаковки переопределить невозможно  
  
 При компиляции для каждого управляемого класса определяется оператор преобразования, который обеспечивает поддержку неявной упаковки.  Переопределение этого оператора не допускается.  
  
 Дополнительные сведения см. в разделе [Неявная упаковка](../../windows/boxing-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3638:  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```