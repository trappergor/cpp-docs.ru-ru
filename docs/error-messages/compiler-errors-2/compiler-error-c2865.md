---
title: Ошибка компилятора C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: e95714f7a10c1c25562e8b12025ede486e66cff8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532757"
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865

«функция»: недопустимое сравнение для дескриптора_или_указателя

Вы можете сравнить ссылки на [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или управляемых ссылочных типов только на предмет равенства, чтобы увидеть, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).

Невозможно сравнить их для сортировки, так как среда выполнения .NET может переместить управляемые объекты в любой момент изменить результат теста.