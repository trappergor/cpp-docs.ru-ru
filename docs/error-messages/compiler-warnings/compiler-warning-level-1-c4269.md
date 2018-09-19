---
title: Предупреждение компилятора (уровень 1) C4269 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dc986c98028530b8a5d4d25047305fd1a8effef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027285"
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