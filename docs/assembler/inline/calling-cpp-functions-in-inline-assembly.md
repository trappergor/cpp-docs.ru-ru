---
title: Вызов функций C++ во встроенной сборке | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4717ae24dc1a0b6f51f7a00f68f6569c2f988c65
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678948"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C++ во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Блок `__asm` может вызывать только глобальные функции C++, которые не являются перегруженными. При вызове перегруженной глобальной функции C++ или функции-члена C++ компилятор выдает ошибку.

Также можно вызывать любые функции, объявленные с **extern «C»** компоновки. Это позволяет `__asm` блок в программе C++ может вызывать функции библиотеки C, так как все стандартных файлах заголовков функции библиотеки для объявляются **extern «C»** компоновки.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>