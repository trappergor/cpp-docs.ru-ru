---
title: Предупреждение компилятора (уровень 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 8ac00d3d57f8cf7d6c85f3106dbe9b8c3cb9adf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162924"
---
# <a name="compiler-warning-level-1-c4342"></a>Предупреждение компилятора (уровень 1) C4342

изменение поведения: вызвана*функция "Function*", но в предыдущих версиях был вызван оператор-член

В версиях Visual C++ , предшествующих visual Studio 2002, был вызван член, но это поведение было изменено, и компилятор теперь находит наилучшее соответствие в области пространства имен.

Если обнаружен оператор-член, компилятор ранее не рассматривал никаких операторов области пространства имен. Если в области видимости пространства имен есть лучшее совпадение, текущий компилятор правильно вызывает его, тогда как предыдущие компиляторы не рассчитают его.

Это предупреждение следует отключить после успешного переноса кода в текущую версию.  Компилятор может давать ложные срабатывания, создавая это предупреждение для кода, в котором нет изменений в поведении.

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
