---
title: "Ошибка средств компоновщика LNK1158 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1158
dev_langs:
- C++
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65be945fdb6747b2b47a105051c9e5c37ef532ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158
не удается запустить «имя_файла»  
  
 Данный исполняемый файл, вызванных [ССЫЛКУ](../../build/reference/linker-command-line-syntax.md) не в каталог, содержащий связь, так и в каталоге, указанном в переменной среды PATH.  
  
 Например, вы получите эту ошибку при попытке использовать параметр PGOPTIMIZE [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) компоновщика на компьютере с 32-разрядной операционной системе.