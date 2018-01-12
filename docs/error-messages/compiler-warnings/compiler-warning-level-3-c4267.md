---
title: "Предупреждение (уровень 3) C4267 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4267
dev_langs: C++
helpviewer_keywords: C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d1d4069bb7b9e2af52d2777c598e6dc737f7043
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4267"></a>Предупреждение компилятора (уровень 3) C4267
var: преобразование из size_t в type; возможна потеря данных  
  
 Компилятор обнаружил преобразование `size_t` в тип меньшего размера.  
  
 Чтобы устранить это предупреждение, используйте `size_t` вместо `type`. Кроме того, можно использовать целочисленный тип размером не меньше `size_t`.  
  
## <a name="example"></a>Пример  
 В следующем примере описано создание предупреждения C4267:  
  
```  
// C4267.cpp  
// compile by using: cl /W4 C4267.cpp  
void Func1(short) {}  
void Func2(int) {}  
void Func3(long) {}  
void Func4(size_t) {}  
  
int main() {  
   size_t bufferSize = 10;  
   Func1(bufferSize);   // C4267 for all platforms  
   Func2(bufferSize);   // C4267 only for 64-bit platforms  
   Func3(bufferSize);   // C4267 only for 64-bit platforms  
   Func4(bufferSize);   // OK for all platforms  
}  
```