---
title: Ошибка компилятора C2725 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2725
dev_langs:
- C++
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a32f2a3255aa0d23f3164d01c0168365ad55c660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236822"
---
# <a name="compiler-error-c2725"></a>Ошибка компилятора C2725
exception: невозможно выдать или перехватить управляемый объект или объект WinRT по значению или ссылке  
  
 Тип управляемого исключения или исключения WinRT неправилен.  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.  
  
```  
// C2725.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
};  
  
int main() {  
   R % r1 = *gcnew R;  
   throw r1;   // C2725  
  
   R ^ r2 = gcnew R;  
   throw r2;   // OK     
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.  
  
```  
// C2725b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception%) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception ^e) {}  
}  
```  
