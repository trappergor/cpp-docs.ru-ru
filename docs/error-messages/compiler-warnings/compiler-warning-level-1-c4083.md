---
title: Предупреждение компилятора (уровень 1) C4083
ms.date: 11/04/2016
f1_keywords:
- C4083
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
ms.openlocfilehash: 6376f6f67370b68f84cad1eadbf7f0ae40de7a16
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200298"
---
# <a name="compiler-warning-level-1-c4083"></a>Предупреждение компилятора (уровень 1) C4083

ожидался "token"; найден идентификатор "идентификатор"

Идентификатор находится в неправильном месте в операторе **#pragma** .

## <a name="example"></a>Пример

```cpp
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

Проверьте синтаксис директив [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) .
