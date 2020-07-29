---
title: Ошибка компилятора C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: a82ee0bead9e4e7a92c16df89eee86288f562de9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216106"
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692

"function_name": в компиляторе C должны быть полностью прототипные функции с параметром "/CLR"

При компиляции для управляемого кода .NET компилятору C требуются объявления функций ANSI. Кроме того, если функция не принимает параметров, она должна явно объявляться **`void`** в качестве типа параметра.
