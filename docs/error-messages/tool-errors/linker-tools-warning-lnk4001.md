---
title: Предупреждение средств компоновщика LNK4001 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf65c00c5c039769a05e009dcfe46ea42633ac4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300362"
---
# <a name="linker-tools-warning-lnk4001"></a>Предупреждение средств компоновщика LNK4001
объектные файлы не указаны; использованы библиотеки  
  
 Компоновщику передан один или несколько LIB-файлы, но не OBJ-файлы.  
  
 Так, как компоновщик не может получить доступ к данным, может обращаться в OBJ-файл, LIB-файл, это предупреждение означает, что необходимо явно указать другие параметры компоновщика. Например, может потребоваться указать [компьютера или](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), или [/Entry](../../build/reference/entry-entry-point-symbol.md) параметры.