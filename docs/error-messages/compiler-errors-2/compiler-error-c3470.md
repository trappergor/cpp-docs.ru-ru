---
title: Ошибка компилятора C3470 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3470
dev_langs:
- C++
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa84934a4f2b072bcc55f325e69549718897aec4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258151"
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