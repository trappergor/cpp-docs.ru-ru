---
title: Ошибка компилятора C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 8775ff6fd78f1092ae931921a2b15ed2f8b166e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214546"
---
# <a name="compiler-error-c3622"></a>Ошибка компилятора C3622

"класс": невозможно создать экземпляр класса, объявленного как "keyword"

Предпринята попытка создания экземпляра класса, помеченного как [абстрактный](../../extensions/abstract-cpp-component-extensions.md). Класс, помеченный как **`abstract`** , может быть базовым классом, но его экземпляр не может быть создан.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3622.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
