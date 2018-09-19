---
title: Предупреждение компилятора (уровень 1) C4544 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4544
dev_langs:
- C++
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7cd274f0d1b595d374e1b108db40a51395b968
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084280"
---
# <a name="compiler-warning-level-1-c4544"></a>Предупреждение компилятора (уровень 1) C4544

declaration: аргумент шаблона по умолчанию пропускается в этом объявлении шаблона

Аргумент шаблона по умолчанию указан в неправильном месте и был пропущен. Аргумент шаблона по умолчанию для шаблона класса может быть указан только в объявлении или определении шаблона класса, но не в члене шаблона класса.

В этом примере показано возникновение ошибки C4545, а в следующем примере приводятся сведения по ее устранению.

```
// C4544.cpp
// compile with: /W1 /LD
template <class T>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T=int>
template <class T1>
struct S<T>::S1 {};   // C4544
```

В этом примере параметр по умолчанию применяется к шаблону класса `S`:

```
// C4544b.cpp
// compile with: /LD
template <class T = int>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T>
template <class T1>
struct S<T>::S1 {};
```