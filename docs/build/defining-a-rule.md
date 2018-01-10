---
title: "Определение правила | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>Определение правила
*Fromext* представляет расширение зависимого файла и *toext* представляет расширение целевого файла.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>Примечания  
 Расширения не учитывают регистр. Макросы могут вызываться для представления *fromext* и *toext*; макросы разворачиваются во время предварительной обработки. Точка (.) выше *fromext* должен находиться в начале строки. Ноль или более пробелов или вкладок стоит двоеточие (:). Он может следовать только пробелы или вкладки, точку с запятой (;) для указания команды, знак решетки (#) для указания комментария или символ перевода строки. Другие пробелы не допускаются. Команды указаны как в блоках описания.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Пути поиска в правилах](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)