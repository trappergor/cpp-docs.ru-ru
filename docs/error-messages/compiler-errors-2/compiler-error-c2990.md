---
title: Ошибка компилятора C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: f7327b7d2b0cc9fa4b617a9a6033116c43db6258
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366333"
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