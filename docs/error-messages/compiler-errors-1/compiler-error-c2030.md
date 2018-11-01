---
title: Ошибка компилятора C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: 217f97d205e1da075277b8b0bc22ff3baab13482
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602180"
---
# <a name="compiler-error-c2030"></a>Ошибка компилятора C2030

деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed

Класс среды выполнения Windows, объявленный как `sealed`, не может содержать защищенный закрытый деструктор. Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы. Дополнительные сведения см. в разделе [классы и структуры ссылки](../../cppcx/ref-classes-and-structs-c-cx.md).

Чтобы устранить эту ошибку, измените тип доступа деструктора.