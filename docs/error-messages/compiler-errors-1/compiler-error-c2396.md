---
title: "Compiler Error C2396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2396"
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

your\_type::operator'type': определяемая пользователем функция преобразования среды CLR или WinRT не является допустимой.Необходимо преобразовать из или в: «T^», «T^%», «T^&», где T \= your\_type  
  
 Функция преобразования в управляемом типе или типе среды выполнения Windows не содержала по крайней мере один параметр, тип которого совпадает с типом, содержащим эту функцию преобразования.  
  
 В следующем примере показано возникновение ошибки C2396 и приводятся сведения по ее устранению.  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```