---
title: Предупреждение компилятора (уровень 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 439c4976f25688fd9220c3f58ceb933266b5f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187513"
---
# <a name="compiler-warning-level-1-c4342"></a>Предупреждение компилятора (уровень 1) C4342

Изменение поведения: "*функция*" вызван, но был вызван оператор-член в предыдущих версиях

В версиях Visual C++ до Visual Studio 2002 член был вызван, но это поведение было изменено, и компилятор теперь обнаруживает наилучшее совпадение в области видимости пространства имен.

Если оператор-член была обнаружена, компилятор ранее не будет учитывать любое пространство имен операторы области видимости. Если имеется более подходящая область видимости пространства имен, текущий компилятор правильно вызывает его, тогда как предыдущие компиляторы пользователей не рассматривает его.

Это предупреждение должно быть отключено, после успешного переноса кода до текущей версии.  Компилятор может получить ложные срабатывания, создавая это предупреждение для кода без изменения поведения.

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