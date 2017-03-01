---
title: "C3550 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 408856c3ebabfdddef34a306d18193d88efcddcb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3550"></a>Ошибка компилятора C3550
только неструктурированный описатель "decltype(auto)" разрешен в этом контексте  
  
 Если `decltype(auto)` используется как заполнитель для возвращаемого типа функции, он должен применяться сам по себе. Невозможно использовать его как часть объявления указателя (`decltype(auto*)`), объявления ссылки (`decltype(auto&)`) или любой другого подобного объявления.  
  
## <a name="see-also"></a>См. также  
 [Авто](../../cpp/auto-cpp.md)
