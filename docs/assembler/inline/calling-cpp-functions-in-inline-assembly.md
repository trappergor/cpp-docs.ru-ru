---
title: Вызов функций C++ во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 781b60c8973593039c0fdfa2f457170e95048597
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192539"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C++ во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

**`__asm`** Блок может вызывать только глобальные функции C++, которые не перегружены. При вызове перегруженной глобальной функции C++ или функции-члена C++ компилятор выдает ошибку.

Можно также вызывать любые функции, объявленные с помощью компоновки **extern "C"** . Это позволяет **`__asm`** блоку в программе C++ вызывать функции библиотеки C, так как все стандартные файлы заголовков объявляют функции библиотеки, чтобы они имели **внешнюю компоновку "C"** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный ассемблер](../../assembler/inline/inline-assembler.md)<br/>
