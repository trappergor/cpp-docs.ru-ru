---
title: Предупреждение компилятора (уровень 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 1b63d1af49a53b7b15cdbae912d79a1b4f0cf787
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230718"
---
# <a name="compiler-warning-level-1-c4269"></a>Предупреждение компилятора (уровень 1) C4269

"идентификатор": автоматические данные, инициализированные с помощью созданного компилятором конструктора по умолчанию, создают ненадежные результаты

**`const`** Автоматический экземпляр нетривиального класса инициализируется с помощью созданного компилятором конструктора по умолчанию.

## <a name="example"></a>Пример

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

Так как этот экземпляр класса создается в стеке, начальное значение `m_data` может быть любым. Кроме того, поскольку это **`const`** экземпляр, значение `m_data` не может быть изменено.
