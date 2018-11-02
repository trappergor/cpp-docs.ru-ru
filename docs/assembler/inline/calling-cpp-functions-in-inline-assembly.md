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
ms.openlocfilehash: 666f7b2a59f0d48a14be54a439b6402f2a4d3128
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458232"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C++ во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Блок `__asm` может вызывать только глобальные функции C++, которые не являются перегруженными. При вызове перегруженной глобальной функции C++ или функции-члена C++ компилятор выдает ошибку.

Также можно вызывать любые функции, объявленные с **extern «C»** компоновки. Это позволяет `__asm` блок в программе C++ может вызывать функции библиотеки C, так как все стандартных файлах заголовков функции библиотеки для объявляются **extern «C»** компоновки.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>