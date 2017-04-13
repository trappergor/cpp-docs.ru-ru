---
title: "Ошибка компилятора C2383 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: faa2aa2c29ea34009f0812a3796d450a6877ca48
ms.lasthandoff: 04/12/2017

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
