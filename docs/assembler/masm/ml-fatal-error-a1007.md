---
title: Неустранимая ошибка ML A1007 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b883fad01943cd8cff71b3da9dee66407ccc93
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055733"
---
# <a name="ml-fatal-error-a1007"></a>Неустранимая ошибка ML A1007
**слишком глубокий уровень вложенности**  
  
 Код на языке ассемблера достигнут предел вложенности. Ограничение составляет 20 уровни, за исключением случаев, оговоренных в противном случае.  
  
 Одно из следующих были вложены слишком глубоко:  
  
-   Директиву высокого уровня, такие как [. Если](../../assembler/masm/dot-if.md), [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md), или [. Во время](../../assembler/masm/dot-while.md).  
  
-   Определение структуры.  
  
-   Директива условной сборки.  
  
-   Определение процедуры.  
  
-   Объект [PUSHCONTEXT](../../assembler/masm/pushcontext.md) директивы (ограничение составляет 10).  
  
-   Определение сегмента.  
  
-   Файл заголовка.  
  
-   Макрос.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)