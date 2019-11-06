---
title: Предупреждение компилятора (уровень 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 84a0d4c541f67742d68c7f08e0dda52ccd350d04
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626713"
---
# <a name="compiler-warning-level-1-c4269"></a>Предупреждение компилятора (уровень 1) C4269

"идентификатор": автоматические данные, инициализированные с помощью созданного компилятором конструктора по умолчанию, создают ненадежные результаты

**Константный** автоматический экземпляр нетривиального класса инициализируется с помощью конструктора по умолчанию, созданного компилятором.

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

Так как этот экземпляр класса создается в стеке, начальное значение `m_data` может быть любым. Кроме того, поскольку это экземпляр **const** , значение `m_data` не может быть изменено.