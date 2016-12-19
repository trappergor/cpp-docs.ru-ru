---
title: "Ошибка компилятора C3883 | Microsoft Docs"
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
  - "C3883"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3883"
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3883
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная" : статический член данных, помеченный как initonly, должен быть инициализирован  
  
 Переменная, помеченная как [initonly](../../dotnet/initonly-cpp-cli.md), не была правильно инициализирована.  
  
 Следующий пример приводит к возникновению ошибки C3883:  
  
```  
// C3883.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   static int staticConst1;   // C3883  
};  
```  
  
 В следующем примере показан возможный способ разрешения данной ошибки.  
  
```  
// C3883b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst2 = 0;  
};  
```  
  
 В следующем примере показано, как выполнить инициализацию в статическом конструкторе:  
  
```  
// C3883c.cpp  
// compile with: /clr /LD  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```