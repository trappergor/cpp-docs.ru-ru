---
title: "Ошибка компилятора C3380 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8789889ab0d9ebe93941a438c286ed718ac4721
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3380"></a>Ошибка компилятора C3380
"класс": недопустимый спецификатор уровня доступа сборки — разрешены только "public" или "private"  
  
 Ключевые слова [public](../../cpp/public-cpp.md) и [private](../../cpp/private-cpp.md) , применяемые к управляемым классам или структурам, определяют возможность предоставления класса посредством метаданных сборки. К классам программы, компилируемой с использованием параметра `public` /clr `private` , могут применяться только ключевые слова [и](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 `ref` И `value` ключевые слова, при использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), указывают, что управляемый класс (в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
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
