---
title: setjmp longjump | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55cf6a2503367777464f09f92e3e3614c3d9f11b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="setjmplongjump"></a>setjmp/longjump
При включении setjmpex.h или setjmp.h, все вызовы [setjmp](../c-runtime-library/reference/setjmp.md) или [longjmp](../c-runtime-library/reference/longjmp.md) приведет к очистки, который вызывает деструкторы и наконец вызывает.  В отличие от x86, где включение файла setjmp.h предложения finally и деструкторы не вызываются.  
  
 Вызов `setjmp` сохраняет текущего указателя стека, неизменяемые регистры и регистры MxCsr.  Вызовы `longjmp` возврат к последнему `setjmp` вызов узла и сбрасывает указатель стека, неизменяемые регистры и MxCsr, в состояние, сохраненное при последней `setjmp` вызова.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)