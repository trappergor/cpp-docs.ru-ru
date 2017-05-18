---
title: "Предупреждение (уровень 1) C4342 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c4a2afbc3ced186b0db63b22b3cc5c2b27204c71
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4342"></a>Предупреждение компилятора (уровень 1) C4342
Изменение поведения: "*функция*" вызван, но в предыдущих версиях был вызван оператор-член  
  
 В версиях Visual C++ до Visual Studio 2002 член был вызван, но это поведение было изменено и компилятор теперь обнаруживает наилучшего соответствия в области видимости пространства имен.  
  
 Оператор-член, если было обнаружено компилятор не будет предварительно рассматривать любое пространство имен операторов области. Если имеется более подходящая область видимости пространства имен, текущий компилятор правильно вызвавшим его пакетом, в то время как предыдущие компиляторы не учитывать его.  
  
 Это предупреждение должно быть отключено после успешного переноса кода в текущую версию.  Компилятор может получить ложный положительный результат, создавая это предупреждение для кода без изменения поведения.  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [компилятора предупреждения выключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Следующий пример приводит к возникновению ошибки C4342:  
  
```cpp  
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
