---
title: Неустранимая ошибка NMAKE U1099 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7be09691de4212d07b1452ffe33725a3978fc053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1099"></a>Неустранимая ошибка NMAKE U1099
переполнение стека  
  
 Обрабатываемый makefile слишком сложен для текущего выделения стека (NMAKE). NMAKE имеет выделение 0x3000 (12K).  
  
 Чтобы увеличить выделение стека NMAKE, следует запустить [editbin/stack](../../build/reference/stack.md) программы с большим параметром стека:  
  
 **EDITBIN/Stack: reserve (NMAKE). EXE-ФАЙЛА**  
  
 где *зарезервировать* — это число больше, чем текущее выделение стека в NMAKE.