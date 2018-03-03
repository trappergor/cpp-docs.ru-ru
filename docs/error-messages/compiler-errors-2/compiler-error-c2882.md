---
title: "Ошибка компилятора C2882 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2882
dev_langs:
- C++
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60fb32a4603e74ed0bd90b5a027019f6fa5f4acd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2882"></a>Ошибка компилятора C2882
«Имя»: Недопустимое использование идентификатора пространства имен в выражении  
  
 Предпринята попытка использования имени пространства имен в выражении.  
  
 Следующий пример приводит к возникновению ошибки C2882:  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```