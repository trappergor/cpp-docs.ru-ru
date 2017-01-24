---
title: "Ошибка компилятора C3828 | Microsoft Docs"
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
  - "C3828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3828"
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип объекта": аргументы размещения не разрешаются при создании экземпляров управляемых классов и классов WinRT  
  
 При создании объекта управляемого типа или типа среды выполнения Windows нельзя использовать формы размещения оператора [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) и [new](../../cpp/new-operator-cpp.md).  
  
 В следующем примере показано возникновение ошибки C3828 и приводятся сведения по ее устранению.  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```