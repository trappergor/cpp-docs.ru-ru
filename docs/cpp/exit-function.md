---
title: "Exit Function | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Exit
dev_langs: C++
helpviewer_keywords: exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9e0d6a7f903d4af39698b2d98c005cbf64515eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exit-function"></a>Функция exit
**Выхода** функции, объявленные в стандартном включаемом файле STDLIB. H, завершает программу C++.  
  
 Значение, указанное в качестве аргумента для **выхода** возвращается операционной системе как возвращаемого кода или завершения программы. Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно.  
  
> [!NOTE]
>  При помощи констант `EXIT_FAILURE` и `EXIT_SUCCESS`, которые определены во включаемом файле STDLIB.H, можно указать, была ли программа завершена успешно или с ошибкой.  
  
 Выдача `return` инструкции от **основной** , аналогичен вызову функции **выйти из** функцию с возвращаемым значением в качестве аргумента.  
  
 Дополнительные сведения см. в разделе [выхода](../c-runtime-library/reference/exit-exit-exit.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)