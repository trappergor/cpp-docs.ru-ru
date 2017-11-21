---
title: "Ошибка компилятора C3857 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3857
dev_langs: C++
helpviewer_keywords: C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e9c553adf8eb9b326bcb2b3b35a381973c9c4a50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3857"></a>Ошибка компилятора C3857
«Тип»: несколько списков параметров типа не допускаются.  
  
 Больше одного шаблона или универсального был указан для того же типа, что не допускается.  
  
 Следующий пример приводит к возникновению ошибки C3857:  
  
```  
// C3857.cpp  
template <class T, class TT>  
template <class T2>    // C3857  
struct B {};  
```  
  
 Возможное решение:  
  
```  
// C3857b.cpp  
// compile with: /c  
template <class T, class TT, class T2>   
struct B {};  
```  
  
 C3857 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C3857c.cpp  
// compile with: /clr  
generic <typename T>  
generic <typename U>  
ref class GC;   // C3857  
```  
  
 Возможное решение:  
  
```  
// C3857d.cpp  
// compile with: /clr /c  
generic <typename U>  
ref class GC;  
```