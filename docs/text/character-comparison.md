---
title: Сравнение символов | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 246801abcb04cc8d9c2fd1a005183501bde240d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612330"
---
# <a name="character-comparison"></a>Сравнение знаков
Следуйте приведенным ниже советам:  
  
-   Сравнение известный старший байт со знаком ASCII работает правильно:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Сравнение двух неизвестных символов необходимо использовать один из макросов, определенных в файле Mbstring.h:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Это гарантирует, что оба байт двухбайтовой сравниваются на предмет равенства.  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Переполнение буфера](../text/buffer-overflow.md)