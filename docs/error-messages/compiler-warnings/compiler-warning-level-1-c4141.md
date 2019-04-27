---
title: Предупреждение компилятора (уровень 1) C4141
ms.date: 11/04/2016
f1_keywords:
- C4141
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
ms.openlocfilehash: bbc2aea86c367c4977c8899e7aa9b8418e7fedcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255671"
---
# <a name="compiler-warning-level-1-c4141"></a>Предупреждение компилятора (уровень 1) C4141

"модификатор" используется несколько раз

## <a name="example"></a>Пример

```
// C4141.cpp
// compile with: /W1 /LD
inline inline void func ();   // C4141
```