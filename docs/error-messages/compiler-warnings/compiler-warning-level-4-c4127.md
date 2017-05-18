---
title: "Ошибка компилятора предупреждение (уровень 4) C4127 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 3e9fb4ed25e51311ec4f6b1d71a249c21d466069
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4127"></a>Предупреждение компилятора (уровень 4) C4127
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
