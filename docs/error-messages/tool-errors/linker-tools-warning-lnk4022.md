---
title: Предупреждение средств компоновщика LNK4022 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cffb9c4c67bc3003b8dcdda0ad3a2e8d55abe932
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300375"
---
# <a name="linker-tools-warning-lnk4022"></a>Предупреждение средств компоновщика LNK4022
не удается найти уникальное соответствие для символа «символ»  
  
 LINK или LIB обнаружено несколько соответствий для данного упрощенного символа и не удалось разрешить неоднозначность. Нет выходного файла (.exe, .dll, .exp или LIB-файл) создается. Это предупреждение сопровождается одно предупреждение [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) для каждого Дублировать символ после чего возникает неустранимая ошибка [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Чтобы устранить это предупреждение, необходимо укажите знак в декорированном виде. Запустите [DUMPBIN](../../build/reference/dumpbin-options.md) на объект для просмотра внутренних имен.