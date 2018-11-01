---
title: Компилятор предупреждение (уровень 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: e898af8f109ed23bd1784df7b39c174bbed675f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552286"
---
# <a name="compiler-warning-level-3-c4159"></a>Компилятор предупреждение (уровень 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>Директива pragma pragma(pop,...): извлечен ранее занесенный в стек идентификатор "*идентификатор*"

## <a name="remarks"></a>Примечания

Исходный код содержит **принудительной** инструкции с идентификатором для директивы pragma, за которым следует **pop** инструкции без идентификатора. В результате *идентификатор* открывшемся окне так что последующие использует из *идентификатор* может привести к непредвиденному поведению.

## <a name="example"></a>Пример

Чтобы устранить это предупреждение, добавьте идентификатор **pop** инструкции. Пример:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```