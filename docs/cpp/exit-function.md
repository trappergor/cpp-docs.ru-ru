---
title: Exit Function | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5767f6b08b4adcd3d1a8d367c6286a746eeecec3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="exit-function"></a>Функция exit
**Выхода** функции, объявленные в стандартном включаемом файле \<stdlib.h >, завершает программу C++.  
  
 Значение, указанное в качестве аргумента для **выхода** возвращается операционной системе как возвращаемого кода или завершения программы. Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно.  
  
> [!NOTE]
>  Можно использовать константы `EXIT_FAILURE` и `EXIT_SUCCESS`, определенного в \<stdlib.h >, чтобы указать на успех или сбой программы.  
  
 Выдача `return` инструкции от **основной** , аналогичен вызову функции **выйти из** функцию с возвращаемым значением в качестве аргумента.  
  
 Дополнительные сведения см. в разделе [выхода](../c-runtime-library/reference/exit-exit-exit.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)