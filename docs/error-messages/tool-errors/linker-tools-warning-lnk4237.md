---
title: Предупреждение средств компоновщика LNK4237 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5acccf52d3738985c7a83432342952af03bf78b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302871"
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237
Указан, указанный при импорте из «dll»; Используйте /SUBSYSTEM:CONSOLE или/SUBSYSTEM: Windows.  
  
 [Указан](../../build/reference/subsystem-specify-subsystem.md) был указан при построении приложения windows (Win32), в котором непосредственно используются один или несколько из следующих:  
  
-   kernel32.dll  
  
-   Gdi32.dll  
  
-   user32.dll  
  
-   одно из DLL-библиотеки msvcrt *.  
  
 Устранить это предупреждение, не указывая **указан**.