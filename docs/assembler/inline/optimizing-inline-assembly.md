---
title: Оптимизация встроенного кода на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: d4956ba12e0bc268d78a895e6cb1ec6e2059262a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166884"
---
# <a name="optimizing-inline-assembly"></a>Оптимизация встроенного кода на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Наличие блока `__asm` в функции влияет на оптимизацию несколькими способами. Во-первых, компилятор не пытается оптимизировать блок `__asm`. То, что написано на языке ассемблера, то и получается. Во-вторых, наличие блока `__asm` затрагивает память регистровых переменных. Компилятор не регистрирует переменные в блоке `__asm`, если содержимое регистра изменяется этим блоком (`__asm`). Наконец, включение языка ассемблера в функцию затрагивает некоторые другие аспекты оптимизации уровня функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>