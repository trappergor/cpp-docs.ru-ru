---
title: "C3282 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 351d42b7fe7a8f94088d452dfb53c233aaabf80a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282
универсальный параметр списки могут появляться только в управляемых или WinRTclasses структуры и функции  
  
 Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в разделе [универсальных типов](../../windows/generics-cpp-component-extensions.md).  
  
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
