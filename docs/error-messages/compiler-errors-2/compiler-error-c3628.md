---
title: "Ошибка компилятора C3628 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3628"
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

«базовый класс»: управляемые классы или классы WinRT поддерживают наследование только открытых методов  
  
 Была предпринята попытка использовать управляемый класс или класс WinRT как [закрытый](../Topic/private%20\(C++\).md) или [защищенный](../Topic/protected%20\(C++\).md) базовый класс.  Управляемый класс или класс WinRT может использоваться только как базовый класс с [открытым](../../cpp/public-cpp.md) доступом.  
  
 В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
  
 В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.  
  
```  
// C3628b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class B {  
};  
  
__gc class D : B {   // C3628, private is the default access level  
  
// The following line resolves the error.  
// __gc class D : public B {  
};  
  
int main() {  
}  
```