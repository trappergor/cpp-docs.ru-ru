---
title: "copyin | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.openlocfilehash: ff466d0ec280d4e31d49328a725da88d87bd2435
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="copyin"></a>copyin
Позволяет потокам обращаться к значению главного потока, для [threadprivate](../../../parallel/openmp/reference/threadprivate.md) переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 `threadprivate` Переменную, которая будет инициализируется значением переменной в основной поток, как она существует до параллельной конструкции.  
  
## <a name="remarks"></a>Примечания  
 `copyin`применяется к следующие директивы:  
  
-   [параллельный](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Пример  
 В разделе [threadprivate](../../../parallel/openmp/reference/threadprivate.md) пример использования `copyin`.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)
