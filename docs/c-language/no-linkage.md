---
title: "Без компоновки | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 278325c1ad1b31ce20b6a17034be5e4731f6da78
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
