---
title: Ошибка компилятора C2990 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0afceb82a58ee5c0a21e39fcaf4ba0a9ee9f2c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066977"
---
# <a name="compiler-error-c2990"></a>Ошибка компилятора C2990

«класс»: не являющего классом типа уже объявлен как тип класса

Неуниверсальный или класс шаблона переопределяет универсальный или шаблонный класс. Проверьте файлы заголовков для конфликтов.

В следующем примере возникает ошибка C2990:

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 также может возникнуть при использовании универсальных шаблонов:

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 также может возникнуть из-за критических изменений в компиляторе Visual C++ для Visual C++ 2005; Компилятор теперь требует несколько объявлений для одного типа совпадала по отношению к спецификации шаблона.

В следующем примере возникает ошибка C2990:

```
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```