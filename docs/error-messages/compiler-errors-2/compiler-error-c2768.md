---
title: Ошибка компилятора C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 9c0fb8fb0a98830aaf061ba980e7bdd7903f25e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257625"
---
# <a name="compiler-error-c2768"></a>Ошибка компилятора C2768

«функция»: Недопустимое использование явных аргументов шаблона

Компилятору не удалось определить, если определение функции должна быть явной специализации шаблона функции или определении функции должна быть новой функции.

Эта ошибка появилась в Visual Studio .NET 2003, в рамках улучшения соответствия компилятора.

Следующий пример приводит к возникновению ошибки C2768:

```
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```