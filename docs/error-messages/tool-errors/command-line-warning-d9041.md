---
title: Предупреждение командной строки D9041 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c22573d26e09e14789f4cbd64d68f4082125c2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298643"
---
# <a name="command-line-warning-d9041"></a>Предупреждение командной строки D9041
Недопустимое значение «значение» для «/ параметр»; предполагается «значение»; Добавьте «/ analyze» в параметры командной строки, при указании этого предупреждения  
  
 Номер предупреждения анализа кода был добавлен **/wd**, **/we**, **/wo**, или **/wl** параметр командной строки без указания **/ analyze** параметр командной строки. Чтобы устранить эту ошибку, либо добавьте **/ analyze** параметр командной строки, или удалите недопустимый номер предупреждения из соответствующего **/w** параметр командной строки.  
  
## <a name="example"></a>Пример  
 Следующий пример командной строки приводит к возникновению предупреждения D9041:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Чтобы устранить предупреждение, добавьте **/ analyze** параметр командной строки. Если **/ analyze** — не поддерживается версией компилятора, удалите недопустимый номер предупреждения из **/wd** параметр.  
  
## <a name="see-also"></a>См. также  
 [Ошибки командной строки с D8000 по D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)