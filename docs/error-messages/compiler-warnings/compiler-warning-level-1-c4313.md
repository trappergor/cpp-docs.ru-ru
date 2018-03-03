---
title: "Ошибка компилятора предупреждение (уровень 1) C4313 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4313
dev_langs:
- C++
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b90fe384ac3396e73eb2fc69aab3a6d48552adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4313"></a>Предупреждение компилятора (уровень 1) C4313
function: описатель формата в строке формата конфликтует с количеством аргументов типа type  
  
 Существует конфликт между указанным форматом и переданным значением. Например, вы передали 64-разрядный параметр неполному описателю формата %d, который ожидает 32-разрядное целое число. Это предупреждение действует только при компиляции кода для 64-разрядных сред.  
  
## <a name="example"></a>Пример  
 В следующем примере кода возникает ошибка C4313 при компиляции для 64-разрядных сред.  
  
```  
// C4313.cpp  
// Compile by using: cl /W1 C4313.cpp  
#include <stdio.h>  
int main() {  
   int * pI = 0;  
   printf("%d", pI);   // C4313 on 64-bit platform code  
   // Try one of the following lines instead:  
   // printf("%p\n", pI);  
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information  
}  
```