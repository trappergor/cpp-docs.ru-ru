---
title: Ошибка компилятора C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 20b08c0d2cd89224ed3d3b8b34915deb947b0b4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205118"
---
# <a name="compiler-error-c2483"></a>Ошибка компилятора C2483

>"*идентификатор*": объект с конструктором или деструктором не может быть объявлен как "Thread"

Это сообщение об ошибке является устаревшим в Visual Studio 2015 и более поздних версиях. В предыдущих версиях переменные, объявленные с помощью атрибута `thread`, не могут инициализироваться с помощью конструктора или другого выражения, которое требует вычисления во время выполнения. Для инициализации данных `thread` требуется статическое выражение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2483 в Visual Studio 2013 и более ранних версиях.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>См. также раздел

[thread](../../cpp/thread.md)
