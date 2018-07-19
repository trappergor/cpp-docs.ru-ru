---
title: Предупреждение (уровень 1) C4342 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df710912338aa540dd2a29f859fc4533445b09b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281291"
---
# <a name="compiler-warning-level-1-c4342"></a>Предупреждение компилятора (уровень 1) C4342
Изменение поведения: "*функция*" вызван, но в предыдущих версиях был вызван оператор-член  
  
 В версиях Visual C++ до Visual Studio 2002 член был вызван, но это поведение было изменено и компилятор теперь обнаруживает наилучшего соответствия в области видимости пространства имен.  
  
 Оператор-член, если было обнаружено компилятор не будет предварительно рассматривать любое пространство имен операторов области. Если имеется более подходящая область видимости пространства имен, текущий компилятор правильно вызвавшим его пакетом, в то время как предыдущие компиляторы не учитывать его.  
  
 Это предупреждение должно быть отключено после успешного переноса кода в текущую версию.  Компилятор может получить ложный положительный результат, создавая это предупреждение для кода без изменения поведения.  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
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