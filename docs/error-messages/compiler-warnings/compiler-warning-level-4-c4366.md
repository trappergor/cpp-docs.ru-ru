---
title: Предупреждение компилятора (уровень 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 18045377210b6c020786ad2ec2e003d0e764e4b5
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683263"
---
# <a name="compiler-warning-level-4-c4366"></a>Предупреждение компилятора (уровень 4) C4366

Результат унарного оператора "оператор" может быть неровным

Если элемент структуры может быть не выделеен из-за упаковки, компилятор выдает предупреждение, когда адрес этого члена назначается для согласованного указателя. По умолчанию все указатели согласовываются.

Чтобы разрешить C4366, измените выравнивание структуры или объявите указатель с помощью ключевого слова [__unaligned](../../cpp/unaligned.md) .

Дополнительные сведения см. в разделе __unaligned и [Pack](../../preprocessor/pack.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4366.

```cpp
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```