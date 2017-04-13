---
title: "Предупреждение (уровень 1) C4910 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8416e456a7d985eb7a3c40addb716ba5c30bf96
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4910"></a>Предупреждение компилятора (уровень 1) C4910
"\<идентификатор настроек": «__declspec(dllexport)» и «extern» несовместимы при явном создании экземпляра  
  
 Явное создание экземпляра шаблона с именем *\<идентификатор настроек* изменено `__declspec(dllexport)` и `extern` ключевые слова. Однако эти ключевые слова являются взаимоисключающими. Ключевое слово `__declspec(dllexport)` означает создание экземпляра класса шаблона, тогда как ключевое слово `extern` не разрешает автоматическое создание экземпляра класса шаблона.  
  
## <a name="see-also"></a>См. также  
 [Явное создание экземпляра](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)
