---
title: Ошибка компилятора C3181 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33d5c42ce7fec65b2b4481b46590396f3af7d97a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252167"
---
# <a name="compiler-error-c3181"></a>Ошибка компилятора C3181
«Тип»: недопустимый операнд для оператора  
  
Передан недопустимый параметр [typeid](../../windows/typeid-cpp-component-extensions.md) оператор. Параметр должен быть управляемым типом.  
  
Обратите внимание, что компилятор использует псевдонимы для собственных типов, которые сопоставляются с типами в среде CLR.  
  
Следующий пример приводит к возникновению ошибки C3181:  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  
