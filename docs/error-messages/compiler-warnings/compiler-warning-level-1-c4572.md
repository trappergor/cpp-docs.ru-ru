---
title: Предупреждение (уровень 1) C4572 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4572
dev_langs:
- C++
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0c0068a3da1033162f90330876d74d62878178
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280472"
---
# <a name="compiler-warning-level-1-c4572"></a>Предупреждение компилятора (уровень 1) C4572
Атрибут [ParamArray] рекомендуется использовать с параметром/CLR, используйте «...» вместо  
  
 Использовался устаревший способ определения переменное число аргументов. При компиляции для среды CLR используйте многоточие вместо <xref:System.ParamArrayAttribute>. Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4572.  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```