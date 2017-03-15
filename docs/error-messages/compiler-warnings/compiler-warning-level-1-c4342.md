---
title: "Предупреждение (уровень 1) C4342 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4755edcc99a9b8fca00972611bbd633a68eb8ec7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4342"></a>Предупреждение компилятора (уровень 1) C4342
изменение поведения: вызвана "функция", но в предыдущих версиях был вызван оператор-член  
  
 В предыдущих версиях Visual C++ вызывался член, но это поведение изменено и компилятор будет искать наилучшего соответствия в области видимости пространства имен.  
  
 Если найден оператор-член, компилятор не будет предварительно рассматривать любое пространство имен операторы области видимости. Если имеется более подходящая область видимости пространства имен, текущий компилятор правильно назовет ее, тогда как предыдущие компиляторы не учитывать его.  
  
 Это предупреждение должно быть отключено после успешного переноса кода в текущую версию.  Компилятор может получить ложный положительный результат, создавая это предупреждение для кода там, где нет изменений поведения.  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Следующий пример приводит к возникновению ошибки C4342:  
  
```  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```
