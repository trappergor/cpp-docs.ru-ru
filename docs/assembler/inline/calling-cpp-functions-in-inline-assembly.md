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
ms.openlocfilehash: f16e466ebb5f31231411eaaf9a1a85bfcc46a34d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169582"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C++ во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Блок `__asm` может вызывать только глобальные функции C++, которые не являются перегруженными. При вызове перегруженной глобальной функции C++ или функции-члена C++ компилятор выдает ошибку.

Можно также вызывать любые функции, объявленные с помощью компоновки **extern "C"** . Это позволяет блоку `__asm` в C++ программе вызывать функции библиотеки C, так как все стандартные файлы заголовков объявляют функции библиотеки, чтобы они имели внешнюю компоновку **"C"** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>
