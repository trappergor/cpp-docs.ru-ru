---
title: Предупреждение (уровень 1) C4655 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6011bf3a2a3bf1718fc15823f2541f49306857c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283267"
---
# <a name="compiler-warning-level-1-c4655"></a>Предупреждение компилятора (уровень 1) C4655
**'**   
 ***символ* ": тип переменной обновился с момента последней сборки или имеются разные объявления**  
  
 Вы изменили или добавили новый тип данных с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.  
  
 Это предупреждение сопровождается ошибкой [Неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки  
  
1.  Верните тип данных в его состояние до ошибки.  
  
2.  В меню **Отладка** выберите команду **Применить изменения кода**.  
  
### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Устранение данного предупреждения без изменения исходного кода  
  
1.  В меню **Отладка** выберите **Остановить отладку**.  
  
2.  В меню **Сборка** выберите **Сборка**.