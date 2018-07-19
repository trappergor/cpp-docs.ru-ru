---
title: Ошибка компилятора C3851 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82104776b2d1153310d0552bd873238333e746f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268841"
---
# <a name="compiler-error-c3851"></a>Ошибка компилятора C3851
"char": универсальное имя символа не может обозначать символ в базовой кодировке  
  
 В коде, скомпилированном как C++, нельзя использовать универсальное имя символа, представляющее символ в основной кодировке исходного кода, вне строки или символьного литерала. Дополнительные сведения см. в разделе [наборов символов](../../cpp/character-sets.md). В коде, скомпилированном как C, нельзя использовать универсальное имя символа для символов в диапазоне от 0x20 до 0x7f, включительно, за исключением 0x24 ("$"), 0x40 ("@") или 0x60 ("`").  
  
 Приведенные ниже примеры кода создают ошибку C3851; также показаны способы ее устранения:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```