---
title: Сравнение символов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b969783a19c0836a8ab81d75820fc688df3ef31e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854955"
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