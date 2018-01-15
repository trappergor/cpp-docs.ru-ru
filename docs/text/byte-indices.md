---
title: "Индексы байтов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 594acadeedad06e9720180c38bd0bcd657391879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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