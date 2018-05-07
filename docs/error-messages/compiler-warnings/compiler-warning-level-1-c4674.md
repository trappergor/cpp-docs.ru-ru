---
title: Предупреждение (уровень 1) C4674 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ede4ac8f8d0af94d998914b8a434cd8b2a9f482
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4674"></a>Предупреждение компилятора (уровень 1) C4674
"метод": требуется объявление как "static" и наличие строго одного параметра  
  
Неправильная сигнатура оператора преобразования. Метод не считается пользовательским преобразованием. Дополнительные сведения об определении операторов см. в разделе [определяемые пользователем операторы (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md) и [пользовательских преобразований (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера будет выдано предупреждение C4674.  
  
```  
// C4674.cpp  
// compile with: /clr /WX /W1 /LD  
ref class G {  
   int op_Implicit(int i) {   // C4674  
      return 0;  
   }  
};  
```  
