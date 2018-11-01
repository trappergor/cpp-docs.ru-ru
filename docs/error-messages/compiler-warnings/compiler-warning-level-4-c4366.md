---
title: Предупреждение компилятора (уровень 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 11fcb0070359201de39ca5f33c83d000e02f0835
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629070"
---
# <a name="compiler-warning-level-4-c4366"></a>Предупреждение компилятора (уровень 4) C4366

Результатом унарного оператора «operator» может быть невыровненным

Если член структуры не выровнен вследствие упаковки, компилятор выдает предупреждение, когда что адреса элемента назначен выровненного указателя. По умолчанию все указатели выравниваются.

Чтобы устранить C4366, изменить выравнивание структуры или объявить указатель с [__unaligned](../../cpp/unaligned.md) ключевое слово.

Дополнительные сведения см. в разделе __unaligned и [пакет](../../preprocessor/pack.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4366.

```
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