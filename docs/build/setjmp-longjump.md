---
title: "setjmp longjump | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3617f70e7c62e1845d8d24e11cebdd7738c507f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
При включении setjmpex.h или setjmp.h, все вызовы [setjmp](../c-runtime-library/reference/setjmp.md) или [longjmp](../c-runtime-library/reference/longjmp.md) приведет к очистки, который вызывает деструкторы и наконец вызывает.  В отличие от x86, где включение файла setjmp.h предложения finally и деструкторы не вызываются.  
  
 Вызов `setjmp` сохраняет текущего указателя стека, неизменяемые регистры и регистры MxCsr.  Вызовы `longjmp` возврат к последнему `setjmp` вызов узла и сбрасывает указатель стека, неизменяемые регистры и MxCsr, в состояние, сохраненное при последней `setjmp` вызова.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)