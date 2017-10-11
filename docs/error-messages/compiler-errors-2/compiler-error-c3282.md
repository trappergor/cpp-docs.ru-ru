---
title: "Ошибка компилятора C3282 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3282
dev_langs:
- C++
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86baad7d8fc0b7dcced75af1453a9695b9b6762c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282
универсальный параметр списки могут использоваться только в управляемых или WinRTclasses, структурах или функциях  
  
 Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в разделе [Универсальные типы](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C3282 и приводятся сведения по ее устранению.  
  
```  
// C3282.cpp  
// compile with: /clr /c  
generic <typename T> int x;   // C3282  
  
ref struct GC0 {  
   generic <typename T> int x;   // C3282  
};  
  
// OK  
generic <typename T>  
ref class M {};  
```
