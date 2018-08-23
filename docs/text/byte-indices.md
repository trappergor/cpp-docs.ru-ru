---
title: Индексы байтов | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5beb69ef7d9d3356eddef40c6bce6483079d934a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590804"
---
# <a name="byte-indices"></a>Индексы байтов
Следуйте приведенным ниже советам:  
  
-   Работа с побайтовым индекса в строку создает проблемы, похожие на те сформулированный работу с указателем. Рассмотрим следующий пример, который проверяет строку на наличие символа обратной косой черты.  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Это может быть индексом младший байт, не старшим байтом, и поэтому не может указывать на `character`.  
  
-   Используйте [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) функция устранены выше:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Это правильно индексирует старшим байтом, поэтому для `character`. `_mbclen` Функция определяет размер символа (1 или 2 байта).  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Последний символ в строке](../text/last-character-in-a-string.md)