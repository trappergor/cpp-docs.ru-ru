---
title: Определение правила | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8ff7c58033ac5f7e42764d185c45c206bf406f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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