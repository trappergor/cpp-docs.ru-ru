---
title: Ошибка средств компоновщика LNK2039 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 954ea12eb9b49c2bdf59b31a1ec2ec2e66c124ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302101"
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