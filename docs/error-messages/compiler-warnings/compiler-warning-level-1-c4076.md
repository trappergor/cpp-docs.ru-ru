---
title: Предупреждение компилятора (уровень 1) C4076 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0a8066b8e79b75f3d5ede37f4e5ad6b61db168
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037883"
---
# <a name="compiler-warning-level-1-c4076"></a>Предупреждение компилятора (уровень 1) C4076

> "*модификатор типа*": не может использоваться с типом "*typename*"

## <a name="remarks"></a>Примечания

Модификатор типа, будь то **автоматический** или **без знака**, нельзя использовать с типом отличный от integer. *модификатор типа* учитывается.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4076; Чтобы устранить проблему, удалите **без знака** модификатор типа:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```