---
title: "Ошибка средств компоновщика LNK2039 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 441765d85ce65a80102ed94b3f4394ae48c0e29f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2039"></a>Ошибка средств компоновщика LNK2039
импортируется ссылочный класс\<тип > ", определенный в another.obj; он должен быть либо импортированных, или определен, но не оба  
  
 Класс ссылки "<`type`>" импортирован в указанный OBJ-файле, но также определяется в другой OBJ-файле. Это условие может вызвать сбой выполнения или другие непредвиденные ситуации.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте ли "`type`" должен быть определен в OBJ-файл и проверьте, является ли строка должна быть импортирована из файла .winmd.  
  
2.  Удалите определение или импорта.  
  
## <a name="see-also"></a>См. также  
 [Ошибки и предупреждения средств компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Ошибка средств компоновщика LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)