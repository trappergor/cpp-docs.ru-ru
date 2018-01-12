---
title: "Скалярные типы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b0915637025e176ee98d01be3991b30b4e6544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="scalar-types"></a>Скалярные типы
Несмотря на то, что обращение к данным может быть обусловлено любой выравнивание, рекомендуется выравнивание данных в исходном во избежание потери производительности (или диапазоне). Перечисления являются константы целых чисел и обрабатываются как 32-разрядных целых чисел. В следующей таблице описаны определения типов и рекомендуемые хранилища для него, как в случае выравнивания с использованием следующих значений:  
  
-   Byte - 8 бит  
  
-   Word - 16 бит  
  
-   Двойное слово - 32 бита  
  
-   Четыре слова — 64-разрядная  
  
-   Word являются восьмеричным - 128 бит  
  
|||||  
|-|-|-|-|  
|Скалярный тип|Тип данных C|Объем памяти (в байтах)|Рекомендуемое выравнивание|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Слово|  
|**UINT16**|**unsigned short**|2|Слово|  
|**INT32**|**int, long**|4|Двойное слово соответственно|  
|**UINT32**|**unsigned int, long без знака**|4|Двойное слово соответственно|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned __int64**|8|Quadword|  
|**FP32 (одинарная точность)**|**float**|4|Двойное слово соответственно|  
|**FP64 (двойной точности)**|**double**|8|Quadword|  
|**УКАЗАТЕЛЬ**|**\***|8|Quadword|  
|`__m64`|**Структура __m64**|8|Quadword|  
|`__m128`|**__m128 структуры**|16|Octaword|  
  
## <a name="see-also"></a>См. также  
 [Типы и хранилище](../build/types-and-storage.md)