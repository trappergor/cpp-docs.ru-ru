---
title: Ошибка средств компоновщика LNK1158 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1158
dev_langs:
- C++
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71cee2a31d1a7b05104031fbf41e8e3addb82d7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158
не удается запустить «имя_файла»  
  
 Данный исполняемый файл, вызванных [ССЫЛКУ](../../build/reference/linker-command-line-syntax.md) не в каталог, содержащий связь, так и в каталоге, указанном в переменной среды PATH.  
  
 Например, вы получите эту ошибку при попытке использовать параметр PGOPTIMIZE [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) компоновщика на компьютере с 32-разрядной операционной системе.