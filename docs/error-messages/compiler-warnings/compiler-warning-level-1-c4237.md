---
title: Предупреждение компилятора (уровень 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: 04fcb99e1dd1e348716e25affb22b54079d53aa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207387"
---
# <a name="compiler-warning-level-1-c4237"></a>Предупреждение компилятора (уровень 1) C4237

Ключевое слово «ключевое_слово» еще не поддерживается, но зарезервировано для будущего использования

В спецификации C++ ключевое слово не реализован в компиляторе Visual C++, но ключевое слово не доступен в качестве определяемого пользователем символа.

В следующем примере возникает ошибка C4237:

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```