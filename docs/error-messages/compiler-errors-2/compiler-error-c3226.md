---
title: "Ошибка компилятора C3226 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3226
dev_langs: C++
helpviewer_keywords: C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4dbba2964b99dd059f27d4bc4917a74fec664ab2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3226"></a>Ошибка компилятора C3226
Объявление шаблона недопустимо внутри универсального объявления  
  
 Используйте универсальное объявление в универсальном классе.  
  
 Следующий пример приводит к возникновению ошибки C3226:  
  
```  
// C3226.cpp  
// compile with: /clr  
generic <class T>  
ref class C {  
   template <class T1>   // C3226  
   ref struct S1 {};  
};  
```  
  
 В следующем примере показано возможное решение:  
  
```  
// C3226b.cpp  
// compile with: /clr /c  
generic <class T>  
ref class C {  
   generic <class T1>  
   ref struct S1 {};  
};  
```