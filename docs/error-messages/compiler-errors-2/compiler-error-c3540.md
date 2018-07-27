---
title: Ошибка компилятора C3540 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3540
dev_langs:
- C++
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27bae73d387612be41d8462bf0e5e0d82516ba1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256048"
---
# <a name="compiler-error-c3540"></a>Ошибка компилятора C3540
«Тип»: невозможно применить sizeof к типу, который содержит «auto»  
  
 [Sizeof](../../cpp/sizeof-operator.md) оператор не может применяться к указанному типу, так как он содержит `auto` спецификатор.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3540.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/ Zc: auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [Оператор sizeof](../../cpp/sizeof-operator.md)