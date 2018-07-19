---
title: Директивы препроцессору | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 711e28a569cefbb500a98ab33cd22c527a5fd7c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382907"
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