---
title: Ошибка компилятора C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: f9090e098d7f523bf7bc12b7fa4d9312f6ca5466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212908"
---
# <a name="compiler-error-c2030"></a>Ошибка компилятора C2030

деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed

Класс среда выполнения Windows, объявленный как, **`sealed`** не может иметь защищенный закрытый деструктор. Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы. Подробные сведения см. в статье [Ref classes and structs (C++/CX)](../../cppcx/ref-classes-and-structs-c-cx.md) (Ссылочные классы и структуры (C++/CX)).

Чтобы устранить эту ошибку, измените тип доступа деструктора.
