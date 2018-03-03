---
title: "Предупреждение средств компоновщика LNK4237 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 718058dae02e9dfe9b653abea91993ec6662f5c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237
Указан, указанный при импорте из «dll»; Используйте /SUBSYSTEM:CONSOLE или/SUBSYSTEM: Windows.  
  
 [Указан](../../build/reference/subsystem-specify-subsystem.md) был указан при построении приложения windows (Win32), в котором непосредственно используются один или несколько из следующих:  
  
-   kernel32.dll  
  
-   Gdi32.dll  
  
-   user32.dll  
  
-   одно из DLL-библиотеки msvcrt *.  
  
 Устранить это предупреждение, не указывая **указан**.