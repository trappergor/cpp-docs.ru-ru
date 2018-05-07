---
title: Ошибка компилятора C3541 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3541
dev_langs:
- C++
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2440d1ab91cda00240d99d2188365754bd34fb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3541"></a>Ошибка компилятора C3541
«Тип»: typeid нельзя применять к типу, который содержит «auto»  
  
 [Typeid](../../windows/typeid-cpp-component-extensions.md) оператор не может применяться к указанному типу, так как он содержит `auto` спецификатор.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3541.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/ Zc: auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../../windows/typeid-cpp-component-extensions.md)