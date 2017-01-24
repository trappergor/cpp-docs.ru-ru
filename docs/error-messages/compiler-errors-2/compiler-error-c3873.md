---
title: "Ошибка компилятора C3873 | Microsoft Docs"
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
  - "C3873"
helpviewer_keywords: 
  - "C3873"
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3873
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"char": этот символ недопустим как первый символ идентификатора  
  
 Компилятор C\+\+ следует стандарту C \+\+ 11 в отношении разрешенных символов в идентификаторе. В идентификаторе можно использовать только определенные диапазоны символов и универсальных имен символов. Дополнительные ограничения применяются к начальному символу идентификатора. Дополнительные сведения и список разрешенных символов и диапазонов универсальных имен символов см. в разделе [Идентификаторы C\+\+](../../cpp/identifiers-cpp.md).  
  
 Диапазон разрешенных символов в идентификаторе шире, чем при компиляции кода C\+\+\/CLI. Идентификаторы в коде, скомпилированном с помощью \/clr, должны соответствовать [стандарту ECMA\-335: Common Language Infrastructure \(CLI\)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Следующий пример приводит к возникновению ошибки C3873:  
  
```  
// C3873.cpp int main() { int \u036F_abc;   // C3873, not in allowed range for initial character int abc_\u036F;   // OK, in allowed range for non-initial character }  
```