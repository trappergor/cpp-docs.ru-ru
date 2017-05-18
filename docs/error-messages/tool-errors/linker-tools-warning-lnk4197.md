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
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3ef9f4ad3822e6fbe3f323fe985b3d4330753df4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4197"></a>Предупреждение средств компоновщика LNK4197
Экспорт «имя» указан несколько раз. с помощью первой спецификации  
  
 Экспорт определено несколько и различными способами. Компоновщик использует первую спецификацию и игнорирует остальные.  
  
 Если выполняется перестроение библиотеки времени выполнения C, это сообщение можно проигнорировать.  
  
 Если экспорт был указан несколько раз точно так же, компоновщик не выдаст предупреждение.  
  
 Например следующее содержимое DEF-файла вызовет предупреждение:  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указан тот же Экспорт в командной строке (путем экспорта:) и в файле DEF.  
  
2.  Тот же Экспорт указана два раза в DEF-файл с различными атрибутами.
