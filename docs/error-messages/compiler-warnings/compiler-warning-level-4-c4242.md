---
title: "Предупреждение компилятора (уровень 4) C4242 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4242"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4242"
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровень 4) C4242
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": преобразование "тип1" в "тип2", возможна потеря данных  
  
 Различные типы.  В результате преобразования типов возможна потеря данных.  В процессе компиляции выполняется преобразование типов.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
 Дополнительные сведения об ошибке C4242 см. в разделе [Общие ошибки компилятора](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Следующий пример приводит к возникновению ошибки C4242:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```