---
title: "Предупреждение средств компоновщика LNK4219 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1331931ba2fa7219a27b8f60b185dc3ab9310328
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4219"></a>Предупреждение средств компоновщика LNK4219
Переполнение адресной привязки имя адресной привязки. Целевой «имя целевого символа» находится за пределами диапазона, вносится преобразователь  
  
 Компоновщик вставляет преобразователь в ситуации, когда адрес или смещение не удалось помещается в данной инструкции, поскольку целевой символ находится слишком далеко от расположения инструкции.  
  
 Вы можете переупорядочить образ (с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) вариант, например) во избежание дополнительный уровень косвенного обращения.