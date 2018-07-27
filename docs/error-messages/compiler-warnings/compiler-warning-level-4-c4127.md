---
title: Ошибка компилятора предупреждение (уровень 4) C4127 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c98b2eb42cfc66c27faf74c3d6e46e981851a0a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293651"
---
# <a name="compiler-warning-level-4-c4127"></a>Предупреждение компилятора (уровень 4) C4127
условное выражение является константой  
  
 Управляющее выражение оператора `if` или цикла `while` является константой. Из-за их общих идиоматическое использования тривиальные константы, например 1 или `true` не запускают предупреждение, если они не являются результатом операции в выражении. Если управляющее выражение `while` цикла является константой, так как завершает работу цикла в середине, рассмотрите возможность замены `while` цикл `for` цикла. Можно опустить инициализацию, проверку завершения и шаг приращения цикла `for` цикл, который вызывает цикла неограниченное так же, как `while(1)`, и выйти из цикла из тела `for` инструкции.  
  
 В следующем примере показано два способа C4127 создается и показано, как использовать для цикла избежать этого предупреждения:  
  
```  
// C4127.cpp  
// compile with: /W4  
#include <stdio.h>  
int main() {  
   if (1 == 1) {}   // C4127  
   while (42) { break; }   // C4127  
  
   // OK  
   for ( ; ; ) {  
      printf("test\n");  
      break;  
   }  
}  
```