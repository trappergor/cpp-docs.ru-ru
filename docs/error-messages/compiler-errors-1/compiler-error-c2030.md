---
title: Ошибка компилятора C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: e3f3936e6fd37da16c923cb482f45cec11833b3c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208036"
---
# <a name="compiler-error-c2030"></a>Ошибка компилятора C2030

деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed

Класс среды выполнения Windows, объявленный как `sealed`, не может содержать защищенный закрытый деструктор. Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы. Подробные сведения см. в статье [Ref classes and structs (C++/CX)](../../cppcx/ref-classes-and-structs-c-cx.md) (Ссылочные классы и структуры (C++/CX)).

Чтобы устранить эту ошибку, измените тип доступа деструктора.
