---
title: Предупреждение компилятора (уровень 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 0dcb6163a87a92f33e875dac8b200f414bb36be6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164135"
---
# <a name="compiler-warning-level-1-c4052"></a>Предупреждение компилятора (уровень 1) C4052

объявления функции отличаются; одно из них содержит переменные аргументы

Одно объявление функции не содержит переменных аргументов. Игнорируется.

В следующем примере возникает ошибка C4052.

```c
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```
