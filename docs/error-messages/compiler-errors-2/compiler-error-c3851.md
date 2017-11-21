---
title: "Ошибка компилятора C3851 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3851
dev_langs: C++
helpviewer_keywords: C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed2a62b859e37455041171c81bb6830db372c697
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3851"></a>Ошибка компилятора C3851
"char": универсальное имя символа не может обозначать символ в базовой кодировке  
  
 В коде, скомпилированном как C++, нельзя использовать универсальное имя символа, представляющее символ в основной кодировке исходного кода, вне строки или символьного литерала. Дополнительные сведения см. в разделе [Character Sets](../../cpp/character-sets2.md). В коде, скомпилированном как C, нельзя использовать универсальное имя символа для символов в диапазоне от 0x20 до 0x7f, включительно, за исключением 0x24 ("$"), 0x40 ("@") или 0x60 ("`").  
  
 Приведенные ниже примеры кода создают ошибку C3851; также показаны способы ее устранения:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```