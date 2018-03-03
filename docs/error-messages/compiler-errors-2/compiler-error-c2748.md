---
title: "Ошибка компилятора C2748 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2748
dev_langs:
- C++
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7db053bf9aef4db18b937292821c18d42508b881
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2748"></a>Ошибка компилятора C2748
при создании управляемого массива или массива WinRT следует указать размер массива или инициализатор массива  
  
 Неправильный формат управляемого массива или массива WinRT. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере показано возникновение ошибки C2748 и приводятся сведения по ее устранению.  
  
```  
// C2748.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>();   // C2748  
   // try the following line instead  
   array<int> ^p2 = new array<int>(2);  
}  
```