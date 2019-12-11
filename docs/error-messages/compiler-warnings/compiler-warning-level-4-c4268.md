---
title: Предупреждение компилятора (уровень 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: f3a6497ae7fc2bb3a73684c9dc76401cf96ca3fa
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991307"
---
# <a name="compiler-warning-level-4-c4268"></a>Предупреждение компилятора (уровень 4) C4268

"идентификатор": статические/глобальные данные, инициализированные с помощью конструктора по умолчанию, созданного компилятором, заполняют объект нулями

**Константный** глобальный или статический экземпляр нетривиального класса инициализируется с помощью конструктора по умолчанию, созданного компилятором.

## <a name="example"></a>Пример

```cpp
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

Поскольку этот экземпляр класса является **константой**, значение `m_data` нельзя изменить.
