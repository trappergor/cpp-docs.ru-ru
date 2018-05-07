---
title: Ошибка компилятора C3077 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3077
dev_langs:
- C++
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbd3a1bd590e5eaece557903318f6b94bd65b798
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3077"></a>Ошибка компилятора C3077
"метод_завершения": метод завершения может быть членом только ссылочного типа  
  
 Нельзя объявлять метод завершения с собственным типом или типом значения.  
  
 Дополнительные сведения см. в разделе [деструкторы и методы завершения в разделе: определение и использование классов и структур (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3077.  
  
```  
// C3077.cpp  
// compile with: /clr /c  
value struct vs {  
   !vs(){}   // C3077  
};  
  
ref struct rs {  
protected:  
   !rs(){}   // OK  
};  
```