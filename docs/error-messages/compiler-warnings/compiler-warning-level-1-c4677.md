---
title: Предупреждение компилятора (уровень 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 66b8d42b63bcbf328703523c4eeda7a047f4643c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533020"
---
# <a name="compiler-warning-level-1-c4677"></a>Предупреждение компилятора (уровень 1) C4677

«функция»: подпись не частного члена содержит частный тип сборки «private_type»

Тип, открытым вне сборки использует тип, имеющий закрытый доступ за пределами сборки. Компонент, ссылающийся на открытый тип сборки не будут иметь возможность использовать член типа или члены, ссылающиеся на частный тип сборки.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4677.

```
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```