---
title: Предупреждение компилятора (уровень 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 9a7f42b2dd65644d3f2abec58236a0b93cc6f635
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653847"
---
# <a name="compiler-warning-level-1-c4269"></a>Предупреждение компилятора (уровень 1) C4269

«Идентификатор»: «const» автоматическое данные, инициализированные конструктором по умолчанию, созданный компилятором, непредсказуемы

Объект **const** автоматический экземпляр нетривиального класса инициализирован конструктором по умолчанию, созданный компилятором.

## <a name="example"></a>Пример

```
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

Так как экземпляр класса создан в стеке, начальное значение `m_data` может быть любым. Кроме того, поскольку это **const** экземпляра значение `m_data` не может быть изменено.