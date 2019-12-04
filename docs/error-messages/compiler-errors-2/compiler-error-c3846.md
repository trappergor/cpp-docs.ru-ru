---
title: Ошибка компилятора C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: a4c51ccfc724cf8309044812b287677f0f1a2ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754905"
---
# <a name="compiler-error-c3846"></a>Ошибка компилятора C3846

"символ": невозможно импортировать символ из "Assembly2": AS "Symbol" уже был импортирован из другой сборки "сборка Assembly1"

Не удалось импортировать символ из сборки, на которую указывает ссылка, так как она была ранее импортирована из упоминаемой сборки.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3846:

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Затем скомпилируйте следующий код:

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
