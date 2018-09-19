---
title: Ошибка компилятора C2078 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8de17341bfb1ad5031be04e977ab68ae4ed1bcb5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111515"
---
# <a name="compiler-error-c2078"></a>Ошибка компилятора C2078

слишком много инициализаторов

Количество инициализаторов превышает число инициализируемых объектов.

Компилятор может определить правильное назначение инициализаторов объектов и внутренних объектов при пропуске внутренних фигурных скобок в списке инициализаторов. Полный формат скобок также устраняет неоднозначность и приводит к правильному назначению. Частичный формат скобок может привести к ошибке C2078 из-за неоднозначности при назначении инициализаторов объектам.

В следующем примере показано возникновение ошибки C2078 и приводятся сведения по ее устранению.

```
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}

```