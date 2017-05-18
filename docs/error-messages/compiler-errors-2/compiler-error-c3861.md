---
title: "Ошибка компилятора C3861 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 177890dcd3ff2abf07f5d9e282efd4a9fd7121a7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3861"></a>Ошибка компилятора C3861
identifier: идентификатор не найден  
  
Компилятору не удалось разрешить ссылку на идентификатор даже при поиске с зависимостью от аргументов.  
  
Чтобы устранить эту ошибку, проверьте написание и регистр объявления идентификатора. Убедитесь, что [операторов разрешения области](../../cpp/scope-resolution-operator.md) и пространство имен [с помощью директивы](../../cpp/namespaces-cpp.md#using_directives) используются правильно. Если идентификатор объявляется в файле заголовка, убедитесь, что заголовок включен до ссылки на него. Также проверьте, что идентификатор не исключены по [директивы условной компиляции](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3861:  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Пример  
Классы исключений в стандартной библиотеке C++ теперь находятся в пространстве имен `std`.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```
