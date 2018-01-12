---
title: "Ошибка компилятора C3769 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3769
dev_langs: C++
helpviewer_keywords: C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea13880843f5ca35b8cdda2218f19e5491be504c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3769"></a>Ошибка компилятора C3769
«Тип»: вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса  
  
 Вложенный класс не может иметь имя, совпадающее с именем немедленно включающего класса.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3769.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```