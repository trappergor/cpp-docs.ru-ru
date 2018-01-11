---
title: "Предупреждение командной строки D9041 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9041
dev_langs: C++
helpviewer_keywords: D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 307d290bb525ee879f29853c6823d5b9565aba4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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