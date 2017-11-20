---
title: "Директивы препроцессору | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 39f1e29a2bc8b72d5b2467c248a4d12b63baa26b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="directives-to-the-preprocessor"></a>Директивы препроцессору
Директива указывает препроцессору C выполнять определенное действие в тексте программы перед компиляцией. [Директивы препроцессора](../preprocessor/preprocessor-directives.md) полностью описаны в *справочнике по препроцессору*. В следующем примере используется директива препроцессора `#define`.  
  
```  
#define MAX 100  
```  
  
 Этот оператор указывает компилятору заменять каждое вхождение `MAX` на `100` перед компиляцией. Ниже перечислены директивы препроцессора компилятора C.  
  
|#define|#endif|#ifdef|#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)