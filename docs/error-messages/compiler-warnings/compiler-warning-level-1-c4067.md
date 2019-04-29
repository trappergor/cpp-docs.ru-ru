---
title: Компилятор предупреждение (уровень 1) C4067
ms.date: 11/04/2016
f1_keywords:
- C4067
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
ms.openlocfilehash: 012866e328433ec9511782c26a39265481ff4940
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386516"
---
# <a name="compiler-warning-level-1-c4067"></a>Компилятор предупреждение (уровень 1) C4067

> непредвиденные лексемы следующую директиву препроцессора - требуется newline

## <a name="remarks"></a>Примечания

Компилятор найден и игнорируются дополнительные знаки, следующие за директивой препроцессора. Это может быть вызвано любой непредвиденные символы на то, что основной причиной является лишней точкой с запятой после директивы. Комментарии не вызывают это предупреждение. **/Za** это предупреждение для дополнительные директивы препроцессора, чем значение по умолчанию включает параметр компилятора.

## <a name="example"></a>Пример

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

Чтобы устранить это предупреждение, удалите случайные символы или переместить их в блок комментариев. Некоторые предупреждения C4067 могут быть отключены, удалив **/Za** параметр компилятора.

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```