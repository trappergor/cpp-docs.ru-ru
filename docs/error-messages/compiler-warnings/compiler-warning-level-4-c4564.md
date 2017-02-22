---
title: "Предупреждение компилятора (уровень 4) C4564 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4564"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4564"
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 4) C4564
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

метод "метод" класса "класс" определяет неподдерживаемый параметр по умолчанию "параметр"  
  
 Компилятор обнаружил метод с одним или несколькими параметрами, имеющими значения по умолчанию.  Значение\(я\) по умолчанию для параметров будут игнорироваться при вызове метода; следует явным образом присвоить данным параметрам значения.  Если значения не присвоены данным параметрам явным образом, компилятор С\+\+ вызовет ошибку.  
  
 При наличии следующей библиотеки DLL, созданной в Visual Basic, которая допускает параметры по умолчанию или аргументы метода:  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 И следующий пример С\+\+, в котором используется библиотека DLL, созданная посредством Visual Basic,  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```