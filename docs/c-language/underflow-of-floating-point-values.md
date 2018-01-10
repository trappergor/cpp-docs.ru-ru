---
title: "Потеря значимости значений с плавающей запятой | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ecea42172ed285f24a22cba004fb156784483643
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="underflow-of-floating-point-values"></a>Потеря точности значений с плавающей запятой
**ANSI 4.5.1** Задают ли математические функции значение макроса `ERANGE` для целочисленного выражения `errno` при ошибках потери значимости  
  
 При потере точности числа с плавающей запятой выражение `errno` не получает значения `ERANGE`. Если значение стремится к нулю и, наконец, теряет значимость, значение устанавливается равным 0.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)