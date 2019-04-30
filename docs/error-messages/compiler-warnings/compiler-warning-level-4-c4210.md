---
title: Предупреждение компилятора (уровень 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: 3435e18f60568cad390dcb0ef7900658a21ea959
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401193"
---
# <a name="compiler-warning-level-4-c4210"></a>Предупреждение компилятора (уровень 4) C4210

использовано нестандартное расширение: функцию, заданную в области видимости файла

В расширениях Майкрософт по умолчанию ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)), объявления функций имеют область видимости файла.

```
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

Это расширение может помешать кода в другие компиляторы.