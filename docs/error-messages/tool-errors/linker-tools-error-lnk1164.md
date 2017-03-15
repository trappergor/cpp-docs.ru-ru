---
title: "Ошибка средств компоновщика LNK1164 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1164
dev_langs:
- C++
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
caps.latest.revision: 8
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
ms.openlocfilehash: a68195cf43db3b2b1a8e451c8f02eb7e98ab902c
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1164"></a>Ошибка средств компоновщика LNK1164
раздел выравнивание разделов (number) больше, чем значение/ALIGN  
  
 Размер выравнивания для данного раздела в объектном файле превышает значение, указанное в [/ALIGN](../../build/reference/align-section-alignment.md) параметр. **/ALIGN** значение должно быть степенью 2 и равняться или превышать выравнивание раздела, заданное в объектном файле.  
  
 Перекомпилируйте с меньшего размера выравнивания раздела или увеличьте **/ALIGN** значение.
