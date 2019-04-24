---
title: Ошибка компилятора C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 38b7dd86a57c3cd89811c6489e51fb4271fd7b79
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777150"
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865

«функция»: недопустимое сравнение для дескриптора_или_указателя

Вы можете сравнить ссылки на [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md) или управляемых ссылочных типов только на предмет равенства, чтобы увидеть, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).

Невозможно сравнить их для сортировки, так как среда выполнения .NET может переместить управляемые объекты в любой момент изменить результат теста.