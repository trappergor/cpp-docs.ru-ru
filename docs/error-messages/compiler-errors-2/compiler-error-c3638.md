---
title: Ошибка компилятора C3638 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb1a05323187b4a5dfcc2356da4a1ff8b874de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267094"
---
# <a name="compiler-error-c3638"></a>Ошибка компилятора C3638
«оператор»: стандартные упаковка-преобразование и распаковка-преобразование операторы преобразования не может быть переопределен  
  
 Компилятор определяет оператор преобразования для каждого управляемого класса для поддержки неявная упаковка-преобразование. Этот оператор не может быть переопределен.  
  
 Дополнительные сведения см. в разделе [неявная упаковка-преобразование](../../windows/boxing-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3638:  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```