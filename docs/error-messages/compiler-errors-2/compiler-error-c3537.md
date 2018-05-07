---
title: Ошибка компилятора C3537 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3537
dev_langs:
- C++
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f03f02062e61e4034f0a809784ba571ce532e07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3537"></a>Ошибка компилятора C3537
«Тип»: не может быть приведен к типу, который содержит «auto»  
  
 Нельзя привести переменную к указанному типу, так как содержит тип `auto` ключевое слово и значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) действует параметр компилятора.  
  
## <a name="example"></a>Пример  
 Следующий код вызывает ошибку C3537, поскольку переменные приводятся к типу, содержащему `auto` ключевое слово.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)