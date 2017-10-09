---
title: "Ошибка компилятора C2057 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2057
dev_langs:
- C++
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6e42871d8dd267d08282375de0df9efb4f828734
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2057"></a>Ошибка компилятора C2057
требуется константное выражение  
  
 Контекст требует константное выражение, то есть выражение, значение которого известно во время компиляции.  
  
 Компилятору необходимо знать размер типа во время компиляции, чтобы выделить пространство для экземпляра этого типа.  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2057 и приводятся сведения по ее устранению.  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## <a name="example"></a>Пример  
 Язык C имеет более строгие правила относительно константных выражений.  В следующем примере показано возникновение ошибки C2057 и приводятся сведения по ее устранению.  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```
