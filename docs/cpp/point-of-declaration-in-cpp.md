---
title: "Точка объявления в C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "точка объявления"
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Точка объявления в C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Имя считается объявленным сразу после его декларатора, но перед его \(необязательным\) инициализатором.  \(Дополнительные сведения о деклараторах см. в разделе [Деклараторы](http://msdn.microsoft.com/ru-ru/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).\)  
  
 Рассмотрим следующий пример.  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Если бы точка объявления располагалась *после* инициализации, то локальная переменная `dVar` инициализировалась бы значением 7,0 — значением глобальной переменной `dVar`.  Поскольку это не так, `dVar` инициализируется неопределенным значением.  
  
## См. также  
 [Область](../cpp/scope-visual-cpp.md)