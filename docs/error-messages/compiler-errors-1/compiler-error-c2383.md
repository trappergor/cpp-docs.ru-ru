---
title: "Ошибка компилятора C2383 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2383
dev_langs: C++
helpviewer_keywords: C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f89545b9428bd5e901c72d895b5c23317646c26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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