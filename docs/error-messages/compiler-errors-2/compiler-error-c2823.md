---
title: Ошибка компилятора C2823 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2823
dev_langs:
- C++
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad7336834d38f7236b88debc28035d8f7d68e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236648"
---
# <a name="compiler-error-c2823"></a>Ошибка компилятора C2823  
  
> указан недопустимый шаблон typedef  
  
Шаблоны не допускаются в `typedef` определений.  
  
## <a name="example"></a>Пример  
  
Следующий пример приводит к возникновению ошибки C2823 и показано, как исправить эту ошибку:  
  
```cpp  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```