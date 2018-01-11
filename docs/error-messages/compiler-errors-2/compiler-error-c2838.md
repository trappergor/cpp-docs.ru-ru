---
title: "Ошибка компилятора C2838 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2838
dev_langs: C++
helpviewer_keywords: C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b13ccdc42c9e55268c66758a89eef2af4ae147bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2838"></a>Ошибка компилятора C2838
«член»: Недопустимое полное имя в объявлении члена  
  
 Класс, структура или объединение использует полное доменное имя для повторного объявления является членом другого класса, структуры или объединения.  
  
 Следующий пример приводит к возникновению ошибки C2838:  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```