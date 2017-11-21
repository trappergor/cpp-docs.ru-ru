---
title: "Предупреждение (уровень 3) C4159 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4159
dev_langs: C++
helpviewer_keywords: C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1997fc9b210723c5747f67e3b042987043c5c161
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4159"></a>Предупреждение (уровень 3) C4159 компилятора
\#Директива pragma pragma(pop,...): извлечен ранее занесенный в стек идентификатор «идентификатор»  
  
 Исходный код содержит **принудительной** инструкции с идентификатором директивы pragma, за которым следует **pop** инструкции без идентификатора. В результате ***идентификатор*** является использование стека и последующие ***идентификатор*** может привести к непредвиденному поведению.  
  
 Чтобы избежать этого предупреждения, добавьте идентификатор **pop** инструкции. Пример:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```