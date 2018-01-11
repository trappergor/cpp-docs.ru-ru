---
title: "Ошибка компилятора C2659 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2659
dev_langs: C++
helpviewer_keywords: C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c69af55d7a5fd61508505bd96091ffcbed41c5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2659"></a>Ошибка компилятора C2659
оператор: функция в качестве левого операнда  
  
 Функция находится слева от указанного оператора. Наиболее частая причина этой ошибки состоит в том, что в результате синтаксического анализа компилятор воспринял идентификатор в левой части оператора как функцию, хотя по замыслу разработчика это должна быть переменная. Дополнительные сведения см. в статье Википедии статьи [наиболее важную синтаксического анализа](http://en.wikipedia.org/wiki/Most_vexing_parse). В этом примере показаны объявление функции и определение переменной, которые легко перепутать.  
  
```  
// C2659a.cpp  
// Compile using: cl /W4 /EHsc C2659a.cpp  
#include <string>  
using namespace std;  
  
int main()   
{  
   string string1(); // string1 is a function returning string  
   string string2{}; // string2 is a string initialized to empty   
  
   string1 = "String 1"; // C2659  
   string2 = "String 2";  
}  
```  
  
 Для разрешения этой проблемы измените объявление идентификатора таким образом, чтобы он не воспринимался как объявление функции.  
  
 Ошибка C2659 также может возникать, если функция имеет тип, который не может использоваться в выражениях с левой стороны указанного оператора. Этот пример приводит к возникновению ошибки C2659, когда код присваивает функции указатель на функцию:  
  
```  
// C2659b.cpp  
// Compile using: cl /W4 /EHsc C2659b.cpp  
int func0(void) { return 42; }  
int (*func1)(void);  
  
int main()  
{  
   func1 = func0;  
   func0 = func1; // C2659  
}  
```