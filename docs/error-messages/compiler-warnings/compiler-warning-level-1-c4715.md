---
title: "Предупреждение компилятора (уровень 1) C4715 | Microsoft Docs"
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
  - "C4715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4715"
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function": не все пути выполнения возвращают значение  
  
 Заданная функция потенциально может не возвращать значение.  
  
## Пример  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Чтобы предотвратить появление этого предупреждения измените код таким образом, чтобы все пути назначали возвращаемое значение для функции:  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Вероятно, что код содержит вызов для возвращения не возвращаемой функции, указанный в следующем примере:  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Этот код также создает предупреждение, поскольку компилятору не известно о том, что данная функция `fatal` никогда не возвращалась.  Для предотвращения создания этим кодом сообщения об ошибке, объявите функцию `fatal`, используя [\_\_declspec\(noreturn\)](../../cpp/noreturn.md).