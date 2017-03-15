---
title: "Предупреждение средств компоновщика LNK4219 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ab241e13f266158fa0a7bd09036ab2131718f554
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4219"></a>Предупреждение средств компоновщика LNK4219
Переполнение адресной привязки имя исправления. Целевой «имя целевого символа» находится за пределами диапазона, вставляется преобразователь  
  
 Компоновщик вставляет преобразователь в ситуации, когда адрес или смещение не удалось помещаются в данной инструкции, поскольку целевой символ находится слишком далеко от расположения инструкции.  
  
 Можно переупорядочить образ (с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) вариант, например), чтобы избежать дополнительного уровня косвенного обращения.
