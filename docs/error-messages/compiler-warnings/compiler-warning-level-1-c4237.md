---
title: Предупреждение компилятора (уровень 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: c68e84daa2ca1aa023123203bb851e92758f9e40
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447680"
---
# <a name="compiler-warning-level-1-c4237"></a>Предупреждение компилятора (уровень 1) C4237

Ключевое слово «ключевое_слово» еще не поддерживается, но зарезервировано для будущего использования

Ключевое слово в C++ спецификации не реализован в Microsoft C++ компилятора, но ключевое слово не доступен в качестве определяемого пользователем символа.

В следующем примере возникает ошибка C4237:

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```