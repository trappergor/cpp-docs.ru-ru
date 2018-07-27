---
title: Ошибка компилятора C2530 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b226ef5ca0e839c745e13d4118264a69ca408db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229406"
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