---
title: Предупреждение компилятора (уровень 1) C4920 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4920
dev_langs:
- C++
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4873fcb1e5bb6d712e44b86d6f60589d6c8ddf4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091742"
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

```
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```