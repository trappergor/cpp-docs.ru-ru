---
title: "Компоновка в именах в области видимости блока | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: de093c90e0da4a906d8aefebfb7048733c1a1f1d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-block-scope"></a>Компоновка в именах в области видимости блока
Следующие правила компоновки применяются к именам с областью видимости блока (локальные имена).  
  
-   Имена, объявленные как `extern` имеют внешнюю компоновку, если ранее они были объявлены как **статических**.  
  
-   Все остальные имена с областью видимости блока не имеют компоновки.  
  
## <a name="see-also"></a>См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)
