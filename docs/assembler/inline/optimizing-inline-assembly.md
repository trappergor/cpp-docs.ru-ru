---
title: Оптимизация встроенной сборки | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49660bdc6d2eb84e6e1bbaeb5ebf0d57e484e9e1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687880"
---
# <a name="optimizing-inline-assembly"></a>Оптимизация встроенного кода на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Наличие блока `__asm` в функции влияет на оптимизацию несколькими способами. Во-первых, компилятор не пытается оптимизировать блок `__asm`. То, что написано на языке ассемблера, то и получается. Во-вторых, наличие блока `__asm` затрагивает память регистровых переменных. Компилятор не регистрирует переменные в блоке `__asm`, если содержимое регистра изменяется этим блоком (`__asm`). Наконец, включение языка ассемблера в функцию затрагивает некоторые другие аспекты оптимизации уровня функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>