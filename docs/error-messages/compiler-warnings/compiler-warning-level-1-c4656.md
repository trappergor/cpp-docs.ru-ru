---
title: Предупреждение (уровень 1) C4656 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e76acbdcfeaea027808aeb144afed65f0f8bbbfe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33287219"
---
# <a name="compiler-warning-level-1-c4656"></a>Предупреждение компилятора (уровень 1) C4656
«символ»: тип данных новых или были изменены с момента последней сборки или имеются разные объявления  
  
 Вы добавили или изменили тип данных, сделав его новым для исходного кода с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.  
  
 За этим предупреждением всегда будет следовать [неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки  
  
1.  Верните тип данных в его состояние до ошибки.  
  
2.  В меню **Отладка** выберите команду **Применить изменения кода**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода  
  
1.  В меню **Отладка** выберите **Остановить отладку**.  
  
2.  В меню **Сборка** выберите **Сборка**.