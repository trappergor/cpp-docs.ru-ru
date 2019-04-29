---
title: Ошибка компилятора C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: 2500736f799032aea71173931139404b4406a16a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384352"
---
# <a name="compiler-error-c2914"></a>Ошибка компилятора C2914

«Идентификатор»: невозможно вывести аргумент типа, как аргумент функции является неоднозначным

Компилятор не может определить, какие перегруженные функции следует использовать для аргумента шаблона или универсального.

В следующем примере возникает ошибка C2914:

```
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914 также может возникнуть при использовании универсальных шаблонов.  В следующем примере возникает ошибка C2914:

```
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```