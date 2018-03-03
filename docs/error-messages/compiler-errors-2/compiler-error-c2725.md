---
title: "Ошибка компилятора C2725 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2725
dev_langs:
- C++
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4083d9594e461c08e5de33d8eb60bab3b85c41ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
