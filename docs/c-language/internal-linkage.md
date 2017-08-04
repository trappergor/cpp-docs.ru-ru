---
title: "Внутренняя компоновка | Документация Майкрософт"
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
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 6d693f4d12fcfe048ef16d9eb8e8806a58d62030
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="internal-linkage"></a>Внутренняя компоновка
Если объявление идентификатора области видимости файла для объекта или функции содержит *описатель класса хранения* **static**, такой идентификатор использует внутреннюю компоновку. В противном случае идентификатор имеет внешнюю компоновку. Использование нетерминального параметра *storage-class-specifier* приводится в статье [Классы хранения](../c-language/c-storage-classes.md).  
  
 В пределах одной записи преобразования каждый экземпляр идентификатора с внутренней компоновкой обозначает тот же идентификатор или функцию. Идентификаторы с внутренней компоновкой уникальны для конкретной записи преобразования.  
  
## <a name="see-also"></a>См. также  
 [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)
