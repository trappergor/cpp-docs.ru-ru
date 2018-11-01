---
title: Ошибка компилятора C2659
ms.date: 11/04/2016
f1_keywords:
- C2659
helpviewer_keywords:
- C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
ms.openlocfilehash: b8b6493b01ac2b88ea50ba50157328f59fdbedf9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601660"
---
# <a name="compiler-error-c2659"></a>Ошибка компилятора C2659

оператор: функция в качестве левого операнда

Функция находится слева от указанного оператора. Наиболее частая причина этой ошибки состоит в том, что в результате синтаксического анализа компилятор воспринял идентификатор в левой части оператора как функцию, хотя по замыслу разработчика это должна быть переменная. Дополнительные сведения см. в статье Википедии статье [самые трудные синтаксического анализа](http://en.wikipedia.org/wiki/Most_vexing_parse). В этом примере показаны объявление функции и определение переменной, которые легко перепутать.

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