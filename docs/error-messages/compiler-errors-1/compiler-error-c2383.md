---
title: "Ошибка компилятора C2383 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f6fa7626541f5fcd06bc2c2c513f52ec443ba4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383
"*символ*": аргументы по умолчанию не разрешены для этого символа  
  
 Компилятор C++ не допускает аргументы по умолчанию для указателей на функции.  
  
 Этот код был принят компилятором Visual C++ в версиях до Visual Studio 2005, но теперь он приводит к ошибке. Для кода, который работает во всех версиях Visual C++ не назначается значение по умолчанию является аргументом указателя на функцию.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2383 и показано возможное решение:  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```
