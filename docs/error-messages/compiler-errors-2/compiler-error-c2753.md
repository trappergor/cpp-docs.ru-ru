---
title: "Ошибка компилятора C2753 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2753
dev_langs: C++
helpviewer_keywords: C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd852023fe4e8cf9b1845ed1a4d53f937b039211
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2753"></a>Ошибка компилятора C2753
"*шаблона*": частичная специализация не может соответствовать список аргументов для основного шаблона  
  
 Если в списке аргументов шаблона соответствует списку параметров, компилятор считает его того же шаблона. Определение того же шаблона дважды не допускается.  
  
## <a name="example"></a>Пример
 Следующий пример приводит к возникновению ошибки C2753 и показывает способ по ее устранению.  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```