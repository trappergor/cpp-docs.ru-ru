---
title: "Ошибка компилятора ошибка C3380 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: fbc75caa22d3c46b5a7a487662119a43b27eaf2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3380"></a>Ошибка компилятора C3380
"класс": недопустимый спецификатор уровня доступа сборки — разрешены только "public" или "private"  
  
 При применении к управляемого класса или структуры, [открытый](../../cpp/public-cpp.md) и [частного](../../cpp/private-cpp.md) означают возможность предоставления класса посредством метаданных сборки. Только `public` или `private` может применяться к классу из программы, скомпилированной с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 `ref` И `value` ключевые слова, при использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), указывают, что класс является управляемым (см. [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C3380:  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  

