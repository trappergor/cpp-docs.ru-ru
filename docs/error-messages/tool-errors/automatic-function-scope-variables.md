---
title: Автоматические переменные (область видимости функции)
ms.date: 04/22/2019
helpviewer_keywords:
- automatic variables
- variables, automatic
- functions [C++], scope
- scope, declared within functions
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
ms.openlocfilehash: 60dcfe61be24516b96054532931fb65245ab31d0
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856694"
---
# <a name="automatic-function-scope-variables"></a>Автоматические переменные (область видимости функции)

Переменная, объявленная внутри функции могут использоваться только в пределах этой функции.

```cpp
// LNK2019_AV.cpp
// compile with: /c
void test(void);

static int lnktest3 = 3;
int lnktest4 = 4;

int main() {
   static int lnktest1 = 1;
   int lnktest2 = 2;
   test();
}
```

И потом

```cpp
// LNK2019_AV_2.cpp
// compile with: LNK2019_AV.cpp
// LNK2019 expected
extern int lnktest1;
extern int lnktest2;
extern int lnktest3;
extern int lnktest4;

void test(void) {
   int i = 0;
   i = lnktest1;
   i = lnktest2;
   i = lnktest3;
   i = lnktest4;   // OK
}
```

## <a name="see-also"></a>См. также

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)