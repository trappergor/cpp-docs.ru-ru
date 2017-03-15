---
title: "Приведение в стиле C с использованием параметра /clr (C++/CLI) | Microsoft Docs"
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
  - "C-стиль приведения и /clr"
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Приведение в стиле C с использованием параметра /clr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующий раздел применим только к среде CLR.  
  
 При использовании с типами CLR, компилятор пытается сопоставить приведение в стиле C с одним из перечисленных ниже приведений, в следующем порядке:  
  
1.  const\_cast  
  
2.  safe\_cast  
  
3.  safe\_cast плюс const\_cast  
  
4.  static\_cast  
  
5.  static\_cast плюс const\_cast  
  
 Если ни одно из приведений, перечисленных выше, недопустимо, и если тип выражения и тип целевого объекта являются ссылочными типами CLR, то приведение в стиле C сопоставляется с проверкой во время выполнения \(инструкция MSIL castclass\).  В противном случае приведение в стиле C считается недопустимым, и компилятор создает ошибку.  
  
## Заметки  
 Приведение в стиле C не рекомендуется.  При компилировании с [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md), используйте [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с `const_cast`.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с `safe_cast`.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с `safe_cast` плюс `const_cast`.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с `static_cast`.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с `static_cast` плюс `const_cast`.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 В следующем примере показано приведение в стиле C, которое сопоставляется с проверкой во время выполнения.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 В следующем примере показано недопустимое приведение в стиле C, которое заставляет компилятор выдать ошибку.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## Требования  
 Параметр компилятора: **\/clr**  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)