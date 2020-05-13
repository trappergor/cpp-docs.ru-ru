---
title: Предупреждение компилятора (уровень 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: b587a4ca2a78bc2ac54640adb2b149d97bef4def
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174665"
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
