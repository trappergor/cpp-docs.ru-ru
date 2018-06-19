---
title: Индексы байтов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509e66c7ea458519eaa9dc4f52c8a6b65c789d0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863804"
---
# <a name="byte-indices"></a>Индексы байтов
Используйте следующие рекомендации:  
  
-   Работа с побайтовым индекса в строку создает проблемы аналогичны вызванных работу с указателем. Рассмотрим следующий пример, который выполнял проверку строки для символа обратной косой черты.  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Это может быть индексом младшего байта, а не старшего байта, и поэтому не может указывать на `character`.  
  
-   Используйте [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) функция устранены выше:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Это пример правильно индексирует старшим байтом, поэтому для `character`. `_mbclen` Функция определяет размер символа (1 или 2 байта).  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Последний символ в строке](../text/last-character-in-a-string.md)