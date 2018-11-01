---
title: Предупреждение компилятора (уровень 1) C4185
ms.date: 11/04/2016
f1_keywords:
- C4185
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
ms.openlocfilehash: c4cabeb206da8da9f9157a8f8eee65c1894ce024
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475118"
---
# <a name="compiler-warning-level-1-c4185"></a>Предупреждение компилятора (уровень 1) C4185

неизвестный атрибут #import "атрибут" пропускается

Атрибут не является допустимым атрибутом директивы `#import`. Игнорируется.

## <a name="example"></a>Пример

```
// C4185.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_such_attribute   // C4185
```