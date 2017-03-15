---
title: "Предупреждение средств компоновщика LNK4248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4248"
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Предупреждение средств компоновщика LNK4248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Неразрешенная лексема typeref \(лексема\) для "типа"; образ нельзя запустить  
  
 Тип не имеет определения в метаданных MSIL.  
  
 Ошибка LNK4248 возникает только при наличии объявления переадресации для типа в модуле MSIL \(скомпилированным с использованием **\/clr**\), если при этом модуль MSIL ссылается на тип и компонуется с собственным модулем, у которого есть определение для типа.  
  
 В этой ситуации компоновщик предоставит определение собственного типа в метаданных MSIL, обеспечив таким образом необходимое поведение.  
  
 Однако, если объявление переадресации типа является типом CLR, определение собственного типа компоновщика может быть неправильным.  
  
 Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### Исправление этой ошибки  
  
1.  Предоставьте определение типа в модуле MSIL.  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки LNK4248.  Чтобы устранить ошибку, определите структуру A.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## Пример  
 В следующем примере приведено определение переадресации типа.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки LNK4248.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```