---
title: Коды выхода из NMAKE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e71442e1e36dbd69afa65051cbf08f403bf8b31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367099"
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