---
title: Предупреждение компилятора (уровень 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 3a56e58d9bec1034a55f4e588dbddd0dba03f348
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208031"
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