---
title: "Ошибка компилятора C3076 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3076"
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"экземпляр": нельзя внедрить экземпляр ссылочного типа "тип" в собственный тип  
  
 Машинный тип не может содержать экземпляр типа CLR.  
  
 Для получения дополнительной информации см. [Семантика стека C\+\+ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Пример  
 В следующем примере возникает ошибка C3076.  
  
```  
// C3076.cpp  
// compile with: /clr /c  
ref struct U {};  
  
struct V {  
   U y;   // C3076  
};  
  
ref struct W {  
   U y;   // OK  
};  
```