---
title: "Ошибка компилятора C2144 | Microsoft Docs"
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
  - "C2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2144"
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ошибка синтаксиса: перед "типом" требуется "лексема"  
  
 Компилятор рассчитывал обнаружить параметр `token`, но вместо него обнаружил параметр `type`.  
  
 Данная ошибка могла возникнуть в результате пропуска закрывающей фигурной скобки, правой круглой скобки или двоеточия.  
  
 Ошибка C2144 также может возникать вследствие попытки создать макрос из ключевого слова среды CLR, содержащего символы пробелов.  
  
 Ошибка C2144 также может быть следствием попытки передачи типа.  Дополнительные сведения см. в разделе [Перенаправление типов \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2144:  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2144:  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```