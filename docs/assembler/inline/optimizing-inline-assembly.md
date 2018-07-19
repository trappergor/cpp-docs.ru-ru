---
title: Оптимизация встроенной сборки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c494594e3b7c541487f34fd33359b0e31f73dd61
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050562"
---
# <a name="optimizing-inline-assembly"></a>Оптимизация встроенного кода на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Наличие блока `__asm` в функции влияет на оптимизацию несколькими способами. Во-первых, компилятор не пытается оптимизировать блок `__asm`. То, что написано на языке ассемблера, то и получается. Во-вторых, наличие блока `__asm` затрагивает память регистровых переменных. Компилятор не регистрирует переменные в блоке `__asm`, если содержимое регистра изменяется этим блоком (`__asm`). Наконец, включение языка ассемблера в функцию затрагивает некоторые другие аспекты оптимизации уровня функции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)