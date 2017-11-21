---
title: "Сравнение символов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0b9098dc20c33cccfd64631e7732be0128cb5bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="character-comparison"></a>Сравнение знаков
Используйте следующие рекомендации:  
  
-   Сравнение известного старшего байта со знаком ASCII выполняется правильно:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Для сравнения двух неизвестных символов необходимо использовать один из макросов, определенных в файле Mbstring.h:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Это гарантирует, что оба байт двухбайтовой проверяются на равенство.  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Переполнение буфера](../text/buffer-overflow.md)