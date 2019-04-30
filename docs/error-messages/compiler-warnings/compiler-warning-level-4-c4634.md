---
title: Предупреждение компилятора (уровень 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 7d0e2af13128a201d96aa905d85621e14441a673
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408216"
---
# <a name="compiler-warning-level-4-c4634"></a>Предупреждение компилятора (уровень 4) C4634

Комментарий XML-документа: применить невозможно: причина

Теги XML-документации могут применяться не ко всем конструкциям C++.  Например, нельзя добавить комментарий документации к пространству имен или шаблону.

Дополнительные сведения см. в разделе [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4634.

```
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4634.

```
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```