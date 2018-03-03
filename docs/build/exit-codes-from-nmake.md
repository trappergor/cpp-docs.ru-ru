---
title: "Коды выхода из NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13cbe4806d8b3960cbf80df41c7cce6e7657ba7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exit-codes-from-nmake"></a>Коды выхода из NMAKE
Программа NMAKE возвращает следующие коды выхода:  
  
|Код|Значение|  
|----------|-------------|  
|0|Нет ошибок (возможно предупреждение)|  
|1|Не завершен процесс построения (выдан только при использовании/k)|  
|2|Ошибки в программе, возможно из-за одного из следующих действий:|  
||-Синтаксическая ошибка в файле makefile|  
||-Ошибка или код выхода из команды|  
||-Прерывание пользователем|  
|4|Системная ошибка: недостаточно памяти|  
|255|Целевой объект актуален не (выдан только при использовании/q)|  
  
## <a name="see-also"></a>См. также  
 [Запуск программы NMAKE](../build/running-nmake.md)