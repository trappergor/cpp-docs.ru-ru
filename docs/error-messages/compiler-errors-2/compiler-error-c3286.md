---
title: "Ошибка компилятора C3286 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80cda9575b604c9dd8e0000428c2d32a487079dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3286"></a>Ошибка компилятора C3286  
  
> "*описатель*": переменной итерации не может иметь любой спецификаторов класса хранения  
  
Класс хранения не может указываться для переменной итерации. Дополнительные сведения см. в разделе [классы хранения (C++)](../../cpp/storage-classes-cpp.md) и [для каждой из них, в](../../dotnet/for-each-in.md).  
  
## <a name="example"></a>Пример  
  
В следующем примере возникает ошибка C3286 и также показано правильное использование.  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```