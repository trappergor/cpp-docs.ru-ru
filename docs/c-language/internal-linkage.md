---
title: "Внутренняя компоновка | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d54a7efdf80d9f1ee26d6954cca7f4e6efe8f71f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="internal-linkage"></a>Внутренняя компоновка
Если объявление идентификатора области видимости файла для объекта или функции содержит *описатель класса хранения* **static**, такой идентификатор использует внутреннюю компоновку. В противном случае идентификатор имеет внешнюю компоновку. Использование нетерминального параметра *storage-class-specifier* приводится в статье [Классы хранения](../c-language/c-storage-classes.md).  
  
 В пределах одной записи преобразования каждый экземпляр идентификатора с внутренней компоновкой обозначает тот же идентификатор или функцию. Идентификаторы с внутренней компоновкой уникальны для конкретной записи преобразования.  
  
## <a name="see-also"></a>См. также  
 [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)