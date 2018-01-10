---
title: "Предупреждение компилятора C4430 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4430
dev_langs: C++
helpviewer_keywords: C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36bf5954387f37ed9527051f900c54ff93da1c6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4430"></a>Предупреждение компилятора C4430
отсутствует спецификатор типа — предполагается int. Примечание: C++ не поддерживает int по умолчанию  
  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: все объявления должны явно указывать тип; int больше не предполагается.  
  
 C4430 всегда выдается как ошибка.  Можно отключить это предупреждение с `#pragma warning` или **/wd**; в разделе [предупреждение](../../preprocessor/warning.md) или  [ /w, помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, / wv, / WX (порог предупреждений)](../../build/reference/compiler-option-warning-level.md)для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4430.  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```