---
title: "Предупреждение (уровень 4) C4408 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4408
dev_langs: C++
helpviewer_keywords: C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4c1d585283428536e0f5faabad25e3a84cb2a6f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4408"></a>Предупреждение компилятора (уровень 4) C4408
anonymousstruct или объединение не объявляет никаких элементов данных  
  
 У анонимной структуры или объединения должен быть по крайней мере один элемент данных.  
  
 Следующий пример приводит к возникновению ошибки C4408.  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```