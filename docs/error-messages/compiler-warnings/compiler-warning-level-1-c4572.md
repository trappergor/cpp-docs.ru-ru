---
title: Предупреждение компилятора (уровень 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: e32509e4d32eef4f53b8d43a7db769844f1182c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397241"
---
# <a name="compiler-warning-level-1-c4572"></a>Предупреждение компилятора (уровень 1) C4572

Атрибут [ParamArray] не рекомендуется использовать с/CLR, используйте «...» Вместо этого

Использовался устаревший способ определения переменное число аргументов. При компиляции для среды CLR, используйте многоточие вместо <xref:System.ParamArrayAttribute>. Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C++Выполняет) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4572.

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```