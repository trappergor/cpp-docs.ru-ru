---
title: "Предупреждение средств компоновщика LNK4001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7c00778af6740f1941b8f62836d4a169a1ca8f6b
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4001"></a>Предупреждение средств компоновщика LNK4001
не указаны объектные файлы; использованы библиотеки  
  
 Компоновщику передан один или несколько LIB-файлов, но не OBJ-файлы.  
  
 Поскольку компоновщик не может получить доступ к данным в LIB-файл, он может обращаться в OBJ-файле, это предупреждение означает, что необходимо явным образом указать другие параметры компоновщика. Например, может понадобиться указать [компьютера или](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), или [/Entry](../../build/reference/entry-entry-point-symbol.md) параметры.
