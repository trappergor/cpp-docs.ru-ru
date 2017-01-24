---
title: "Ошибка компилятора C3412 | Microsoft Docs"
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
  - "C3412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3412"
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"шаблон": невозможно настроить шаблон в текущей области  
  
 Шаблон не может быть настроен в области класса. Настройка шаблона возможна только в глобальной области или области пространства имен.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3412.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## Пример  
 В следующем примере демонстрируется возможное решение.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```