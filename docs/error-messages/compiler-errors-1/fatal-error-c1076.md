---
title: "Неустранимая ошибка C1076 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 617db809cfaeb4d0e0003a3dfc2e9568726b0c58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1076"></a>Неустранимая ошибка C1076
ограничение компилятора: достигнут предел внутренней кучи; воспользуйтесь /Zm для задания большего значения  
  
 Эта ошибка может возникать при использовании слишком большого числа символов или создании слишком большого числа экземпляров шаблонов.  
  
 Устранение ошибки  
  
1.  Используйте [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) параметр, чтобы задать ограничение памяти компилятора значение, указанное в [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) сообщение об ошибке. Дополнительные сведения, включающие как задать это значение [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], см. в разделе "Примечания" [/Zm (укажите предкомпилированный заголовок предел выделения памяти)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  Если используются 32-разрядные размещенные компиляторы в 64-разрядной операционной системе, используйте 64-разрядные размещенные компиляторы. Дополнительные сведения см. в разделе [как: включить 64-разрядных инструментов Visual C++ в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Удалите неиспользуемые включенные файлы.  
  
4.  Удалите неиспользуемые глобальные переменные — например, вместо объявления большого массива можно использовать динамическое выделение памяти.  
  
5.  Удалите неиспользуемые объявления.  
  
6.  Разбейте крупные функции на более мелкие.  
  
7.  Разбейте крупные классы на более мелкие.  
  
8.  Разделите данный файл на меньшие файлы.  
  
 Если C1076 возникает непосредственно после начала построения, значение, указанное для **/Zm** , возможно, слишком велико для вашей программы. Уменьшить **/Zm** значение.