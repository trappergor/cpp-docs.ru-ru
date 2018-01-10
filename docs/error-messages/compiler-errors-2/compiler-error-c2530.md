---
title: "Ошибка компилятора C2530 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2530
dev_langs: C++
helpviewer_keywords: C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f9ea1b462f2e0b141bdc624d77f548f19c4b71a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530
«Идентификатор»: ссылки должны быть инициализированы  
  
 Следует инициализировать ссылку при ее объявлении, если она еще не объявлена:  
  
-   С помощью ключевого слова [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
-   Как член класса, структуры или объединения (и инициализируется в конструкторе).  
  
-   Как параметр в объявлении или определении функции.  
  
-   Как возвращаемый тип функции.  
  
 Следующий пример приводит к возникновению ошибки C2530:  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```