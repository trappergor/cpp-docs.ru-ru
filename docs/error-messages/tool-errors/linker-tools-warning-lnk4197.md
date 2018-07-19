---
title: Предупреждение средств компоновщика LNK4197 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfef7f0fe2d9cd50fa6a18ad682c3e4d80df99c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300842"
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