---
title: "Компилятор C4656 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: b88f2add0a7b8f365d3617b8eb28eecdfa5a0a26
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4656"></a>Предупреждение компилятора (уровень 1) C4656
«символ»: тип данных новые была изменена с момента последнего построения или имеются разные объявления  
  
 Вы добавили или изменили тип данных, сделав его новым для исходного кода с момента последней успешной сборки. Функция "Изменить и продолжить" не поддерживает изменения существующих типов данных.  
  
 Это предупреждение всегда должны следовать [Неустранимая ошибка C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Дополнительные сведения см. в разделе [поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Удаление данного предупреждения без завершения текущего сеанса отладки  
  
1.  Верните тип данных в его состояние до ошибки.  
  
2.  В меню **Отладка** выберите команду **Применить изменения кода**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода  
  
1.  В меню **Отладка** выберите **Остановить отладку**.  
  
2.  В меню **Сборка** выберите **Сборка**.
