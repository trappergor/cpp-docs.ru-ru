---
title: Ошибка компилятора C3755 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3602f78659e58de9dc394f6887901c46de8de60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3755"></a>Ошибка компилятора C3755
«делегат»: делегат не могут быть определены  
  
 Объект [delegate (расширения компонентов C++)](../../windows/delegate-cpp-component-extensions.md) может быть объявлен, но не определен.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3755.  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## <a name="example"></a>Пример  
 C3755 также может возникать при попытке создания шаблона делегата. Следующий пример приводит к возникновению ошибки C3755.  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```