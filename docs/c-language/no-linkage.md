---
title: Без компоновки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc6515020272d19a9b9efca7341293be4983a56
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="no-linkage"></a>Без компоновки
Если объявление идентификатора в блоке не содержит спецификатор класса хранения `extern`, этот идентификатор не имеет компоновки и уникален для функции.  
  
 Следующие идентификаторы не имеют компоновки:  
  
-   идентификатор, объявленный в качестве нечто отличного от объекта или функции;  
  
-   идентификатор, объявленный в качестве параметра функции;  
  
-   идентификатор области видимости блока для объекта, объявленного без спецификатора класса хранения `extern`.  
  
 Если идентификатор не имеет компоновки, повторное объявление того же имени (в деклараторе или спецификаторе типа) на том же уровне области видимости приводит к появлению ошибки переопределения символов.  
  
## <a name="see-also"></a>См. также  
 [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)