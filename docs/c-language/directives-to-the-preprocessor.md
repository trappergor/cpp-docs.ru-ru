---
title: "Директивы препроцессору | Документация Майкрософт"
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
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0c3e8919083d3f5f3ab6345de0a2a6817b93205e
ms.lasthandoff: 02/24/2017

---
# <a name="directives-to-the-preprocessor"></a>Директивы препроцессору
Директива указывает препроцессору C выполнять определенное действие в тексте программы перед компиляцией. [Директивы препроцессора](../preprocessor/preprocessor-directives.md) полностью описаны в *справочнике по препроцессору*. В следующем примере используется директива препроцессора `#define`.  
  
```  
#define MAX 100  
```  
  
 Этот оператор указывает компилятору заменять каждое вхождение `MAX` на `100` перед компиляцией. Ниже перечислены директивы препроцессора компилятора C.  
  
|#define|#endif|#ifdef|#линия|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)
