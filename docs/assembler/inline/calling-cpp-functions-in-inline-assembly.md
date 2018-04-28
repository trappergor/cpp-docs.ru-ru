---
title: Вызов функций C++ во встроенной сборке | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ffbd8038d240bc2ab0240d172d914790b6ca02ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="calling-c-functions-in-inline-assembly"></a>Вызов функций C++ во встроенном коде на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Блок `__asm` может вызывать только глобальные функции C++, которые не являются перегруженными. При вызове перегруженной глобальной функции C++ или функции-члена C++ компилятор выдает ошибку.  
  
 Также можно вызывать любые функции, объявленной с **extern «C»** компоновки. Это позволяет `__asm` блок в программе C++ для вызова функции библиотеки C, поскольку все файлы стандартный заголовок объявления функции библиотеки **extern «C»** компоновки.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)