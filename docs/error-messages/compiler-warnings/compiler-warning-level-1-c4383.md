---
title: Предупреждение компилятора (уровень 1) C4383 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e4ac56b4f94ee6ff7e6ade01dfadca0c00a92db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094849"
---
# <a name="compiler-warning-level-1-c4383"></a>Предупреждение компилятора (уровень 1) C4383

«оператор_разыменовывания_экземпляра»: значение разыменования дескриптора может измениться, если существует определенный пользователем оператор» оператор "; Запишите оператор в виде статической функции явное операнд

Когда вы добавляете является переопределением экземпляр определяемого пользователем оператора разыменования в управляемом типе, вы потенциально переопределить возможность возврата объекта в дескрипторе типа оператор разыменования. Рассмотрите возможность написания пользовательских статического оператор разыменования.

Дополнительные сведения см. в разделе [оператор дескриптора объекта (^)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) и [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).

Кроме того оператор экземпляра не доступны в другие компиляторы языка с помощью ссылочных метаданных. Дополнительные сведения см. в разделе [определяемые пользователем операторы (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4383.

```
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```