---
title: "Предупреждение средств компоновщика LNK4001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4001
dev_langs: C++
helpviewer_keywords: LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb73e0c62a49fe5190103987277483d29af71fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4001"></a>Предупреждение средств компоновщика LNK4001
объектные файлы не указаны; использованы библиотеки  
  
 Компоновщику передан один или несколько LIB-файлы, но не OBJ-файлы.  
  
 Так, как компоновщик не может получить доступ к данным, может обращаться в OBJ-файл, LIB-файл, это предупреждение означает, что необходимо явно указать другие параметры компоновщика. Например, может потребоваться указать [компьютера или](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), или [/Entry](../../build/reference/entry-entry-point-symbol.md) параметры.