---
title: Ошибка компилятора C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: dd4374c1a577c4c39c5dec107ed5025d7cdc79c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201700"
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865

"функция": недопустимое сравнение для handle_or_pointer

Можно сравнить ссылки на [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md) или управляемые ссылочные типы только для проверки на равенство, чтобы определить, ссылаются ли они на один и тот же объект (= =) или на разные объекты (! =).

Их нельзя сравнить для упорядочения, так как среда выполнения .NET может перемещать управляемые объекты в любое время, изменяя результат теста.
