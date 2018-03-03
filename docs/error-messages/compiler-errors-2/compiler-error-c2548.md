---
title: "Ошибка компилятора C2548 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2548
dev_langs:
- C++
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf1edb19170cfe4bac49fbc5108d0d4a7e8be8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2548"></a>Ошибка компилятора C2548
«класс::член»: отсутствует параметр по умолчанию для параметра  
  
 Список параметров по умолчанию отсутствует параметр. Если указан параметр по умолчанию в любом месте в списке параметров, необходимо определить параметры по умолчанию для всех последующих параметров.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2548:  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```