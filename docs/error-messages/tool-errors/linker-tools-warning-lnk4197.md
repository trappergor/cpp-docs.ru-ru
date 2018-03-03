---
title: "Предупреждение средств компоновщика LNK4197 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1fadbf2ba5b18004f0e89142c88a68437842a92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4197"></a>Предупреждение средств компоновщика LNK4197
Экспорт «имя» указан несколько раз. использована первая спецификация  
  
 Экспорт определено несколько и различными способами. Компоновщик использует первую спецификацию и игнорирует остальные.  
  
 Если выполняется перестроение библиотеки времени выполнения C, это сообщение можно проигнорировать.  
  
 Если экспорт был указан несколько раз точно так же, компоновщик не выдаст предупреждение.  
  
 Например следующее содержимое DEF-файла для перевода этого предупреждения:  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указан тот же Экспорт и в командной строке (путем экспорта:) и в файле DEF.  
  
2.  Тот же Экспорт указан в DEF-файл с разными атрибутами дважды.