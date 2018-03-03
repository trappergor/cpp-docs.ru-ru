---
title: "Предупреждение средств компоновщика LNK4022 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e35974a72de349f94f2189f676b6dc955c48fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4022"></a>Предупреждение средств компоновщика LNK4022
не удается найти уникальное соответствие для символа «символ»  
  
 LINK или LIB обнаружено несколько соответствий для данного упрощенного символа и не удалось разрешить неоднозначность. Нет выходного файла (.exe, .dll, .exp или LIB-файл) создается. Это предупреждение сопровождается одно предупреждение [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) для каждого Дублировать символ после чего возникает неустранимая ошибка [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Чтобы устранить это предупреждение, необходимо укажите знак в декорированном виде. Запустите [DUMPBIN](../../build/reference/dumpbin-options.md) на объект для просмотра внутренних имен.