---
title: Компоновка в именах в области видимости блока | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab7758e962c028c4746836e470ee43eaab510f9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418891"
---
# <a name="linkage-in-names-with-block-scope"></a>Компоновка в именах в области видимости блока
Следующие правила компоновки применяются к именам с областью видимости блока (локальные имена).  
  
-   Имена, объявленные как `extern` имеют внешнюю компоновку, если ранее они были объявлены как **статических**.  
  
-   Все остальные имена с областью видимости блока не имеют компоновки.  
  
## <a name="see-also"></a>См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)