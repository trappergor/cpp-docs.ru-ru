---
title: "Диапазоны чтения | Документация Майкрософт"
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
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
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
ms.openlocfilehash: be2c2f555ab004cbb48310d5ad4a6897bd15d408
ms.lasthandoff: 02/24/2017

---
# <a name="reading-ranges"></a>Диапазоны чтения
**ANSI 4.9.6.2** Интерпретация символа дефиса (–), который не является ни первым, ни последним символом в списке сканирования для преобразования % [ в функции `fscanf`  
  
 В следующей строке  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 считывается любое количество символов в диапазоне A-Z в строке, на которую указывает `strptr`.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)
