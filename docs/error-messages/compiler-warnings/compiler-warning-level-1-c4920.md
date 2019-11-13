---
title: Предупреждение компилятора (уровень 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: 7cbb29c8dae24a87fcd5a32b4cf46d7a8ac4c790
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050246"
---
# <a name="compiler-warning-level-1-c4920"></a>Предупреждение компилятора (уровень 1) C4920

enum enum member member=value уже включен в перечисление enum как member=value

Если TLB-файл, который передается в директиву #import, имеет один знак, определенный как минимум в двух перечислениях, это предупреждение указывает, что последующие идентичные знаки игнорируются и будут переведены в комментарии в TLH-файле.

Предположим, TLB-файл имеет следующее содержимое:

```
library MyLib
{
    typedef enum {
        enumMember = 512
    } AProblem;

    typedef enum {
        enumMember = 1024
    } BProblem;
};
```

В следующих примерах возникнет предупреждение C4920:

```cpp
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```