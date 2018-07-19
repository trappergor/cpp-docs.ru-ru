---
title: Предупреждение (уровень 1) C4067 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee6b48327e8754f9388e0df8f43009a5be70c97
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255457"
---
# <a name="compiler-warning-level-1-c4067"></a>Компилятор C4067 предупреждение (уровень 1)

> непредвиденные лексемы следующей директивой препроцессора — ожидание новой строки

## <a name="remarks"></a>Примечания

Компилятором находятся и игнорируются дополнительные знаки, следующие за директивой препроцессора. Это может быть вызвано любые неправильные символы на то, что основной причиной является лишней точкой с запятой после директивы. Комментарии не вызывают это предупреждение. **/Za** данное предупреждение для дополнительные директивы препроцессора, чем значение по умолчанию включает параметр компилятора.

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

Чтобы устранить это предупреждение, удалите лишней символов или переместите их в блок комментариев. Различные предупреждения C4067 могут быть отключены, удалив **/Za** параметр компилятора.

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