---
title: "Ошибка компилятора C3470 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3470
dev_langs: C++
helpviewer_keywords: C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7ae5a2d2d95c3ab6a521493874b416c87d4e5a9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3470"></a>Ошибка компилятора C3470
"тип": класс не может одновременно иметь и индексатор (индексированное свойство по умолчанию), и operator[]  
  
 Тип не может задавать и индексатор по умолчанию, и оператор[].  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3470:  
  
```  
// C3470.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R {  
public:  
   property int default[int] {  
      int get(int i) {  
         return i+1;  
      }  
   }  
  
   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470  
};  
  
int main() {  
   R ^ r = gcnew R;  
   // return r[9] + r["32"] - 42;  
}  
```