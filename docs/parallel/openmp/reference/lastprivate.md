---
title: "lastprivate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: lastprivate
dev_langs: C++
helpviewer_keywords: lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9429a54a21d58be7f2dd1667478ae653da5a8c35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lastprivate"></a>lastprivate
Указывает, что версия контекст внешней переменной приравнивается к закрытой версии поток выполняет последней итерации (конструкция цикла for) или последний раздел (#pragma разделов).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Переменная, которая задана равной закрытой версии поток выполняет последней итерации (конструкция цикла for) или последний раздел (#pragma разделов).  
  
## <a name="remarks"></a>Примечания  
 `lastprivate`применяется к следующие директивы:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Пример  
 В разделе [расписания](../../../parallel/openmp/reference/schedule.md) пример использования `lastprivate` предложения.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)