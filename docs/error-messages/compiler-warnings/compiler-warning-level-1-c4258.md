---
title: Предупреждение компилятора (уровень 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a3ce4c81a86920baddfc1b277df0236a96254be4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478280"
---
# <a name="compiler-warning-level-1-c4258"></a>Предупреждение компилятора (уровень 1) C4258

«переменная»: определение из цикла for игнорируется; используется определение из внешней области видимости»

В разделе [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), переменные, определенные в [для](../../cpp/for-statement-cpp.md) цикл выходят за пределы области после **для** завершения цикла. Это предупреждение возникает, если область, содержащую снова используется переменная с тем же именем, что переменной цикла, но определенные во внешнем цикле **для** цикла. Пример:

```
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```