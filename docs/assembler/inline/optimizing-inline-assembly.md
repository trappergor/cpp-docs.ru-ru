---
title: "Оптимизация встроенной сборки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21f6954ece6adcc60fbb3a8620dd427e7c21042a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-inline-assembly"></a>Оптимизация встроенного кода на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Наличие блока `__asm` в функции влияет на оптимизацию несколькими способами. Во-первых, компилятор не пытается оптимизировать блок `__asm`. То, что написано на языке ассемблера, то и получается. Во-вторых, наличие блока `__asm` затрагивает память регистровых переменных. Компилятор не регистрирует переменные в блоке `__asm`, если содержимое регистра изменяется этим блоком (`__asm`). Наконец, включение языка ассемблера в функцию затрагивает некоторые другие аспекты оптимизации уровня функции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)