---
title: "Перечисления &lt;codecvt&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords: std::codecvt_mode
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: bba1b53abb7286c64bdaf79ec8cb2004ba67a9dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltcodecvtgt-enums"></a>Перечисления &lt;codecvt&gt;
  
##  <a name="codecvt_mode"></a> Перечисление codecvt_mode  
 Задает сведения о конфигурации для аспектов [языкового стандарта](../standard-library/locale-class.md).  
  
```  
enum codecvt_mode {  
    consume_header = 4,  
    generate_header = 2,  
    little_endian = 1  
 };  
```  
  
### <a name="remarks"></a>Примечания  
 Перечисление определяет три константы, которые поставляют сведения о конфигурации для аспектов языкового стандарта, объявленных в [\<codecvt>](../standard-library/codecvt.md). Это могут быть следующие значения:  
  
- `consume_header`, чтобы использовать начальную последовательность заголовка при чтении многобайтовой последовательности и определении порядка байтов следующей многобайтовой последовательности для чтения;  
  
- `generate_header`, чтобы создавать начальную последовательность заголовка при записи многобайтовой последовательности для объявления порядка байтов следующей многобайтовой последовательности для записи;  
  
- `little_endian`, чтобы создавать многобайтовую последовательность в прямом порядке байтов, в отличие от порядка "сначала старший байт" по умолчанию.  
  
 Эти константы можно связывать логическим оператором OR в произвольные сочетания.  
  
## <a name="see-also"></a>См. также  
 [\<codecvt>](../standard-library/codecvt.md)

