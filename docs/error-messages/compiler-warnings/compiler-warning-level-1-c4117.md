---
title: Предупреждение компилятора (уровень 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 2474645a555748b559b1661a2b5327ca1b83e534
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176382"
---
# <a name="compiler-warning-level-1-c4117"></a>Предупреждение компилятора (уровень 1) C4117

имя макроса "имя" является зарезервированным; "команда" игнорируется

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Попытка определения или отмены определения предопределенного макроса.

1. Попытка определения или отмены определения оператора препроцессора **defined**.

В следующем примере возникает ошибка C4117:

```cpp
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```
