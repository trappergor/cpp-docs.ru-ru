---
title: "Увеличение и уменьшение значений указателей | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9eccf65f091c8c5c273f6a65cb7e81b0d386afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="incrementing-and-decrementing-pointers"></a>Увеличение и уменьшение значений указателей
Используйте следующие рекомендации:  
  
-   Укажите старшие байты, а не младшие байты. Обычно небезопасно указатель младший байт. Обычно это безопаснее Просмотр строки вперед, а не в обратном порядке.  
  
-   Существует указатель инкремента или декремента функции и макросы, связанные с переносом на целый знак:  
  
    ```  
    sz1++;  
    ```  
  
     выглядит следующим образом:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` И `_mbsdec` функции правильно увеличения и уменьшения в `character` единиц, независимо от размера знака.  
  
-   Для уменьшения, что требуется указатель на начало строки, как показано ниже:  
  
    ```  
    sz2--;  
    ```  
  
     выглядит следующим образом:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Кроме того, может быть головного указателя на допустимый символ в строке, таким образом, что:  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Необходимо использовать указатель на допустимый старший байт.  
  
-   Может потребоваться сохранить указатель на предыдущий знак быстрее вызовы `_mbsdec`.  
  
## <a name="see-also"></a>См. также  
 [Советы по программированию многобайтовой Кодировки](../text/mbcs-programming-tips.md)   
 [Индексы байтов](../text/byte-indices.md)