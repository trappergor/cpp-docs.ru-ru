---
title: "Неустранимая ошибка C1092 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1092
dev_langs: C++
helpviewer_keywords: C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92309c9299303429c61f84911e180468f6354475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1092"></a>Неустранимая ошибка C1092
Режим "Изменить и продолжить" не поддерживает изменения типов данных; требуется сборка  
  
 Вы изменили или добавили тип данных с момента последней успешной сборки.  
  
-   Изменить и продолжить не поддерживает изменения существующих типов данных, включая определения класса, структуры или перечисления. Необходимо остановить отладку и построить приложение.  
  
-   Изменить и продолжить не поддерживает добавление новых типов данных, если файл базы данных программы, например vc*x*0. pdb (где *x* – основная используемая версия Visual C++) доступен только для чтения. Добавление типов данных, компилятор должен открыть PDB-файл в режиме записи.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Устранение этой ошибки без завершения текущего сеанса отладки  
  
1.  Верните тип данных в его состояние до ошибки.  
  
2.  В меню **Отладка** выберите команду **Применить изменения кода**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода  
  
1.  В меню **Отладка** выберите **Остановить отладку**.  
  
2.  В меню **Сборка** выберите **Сборка**.  
  
 Дополнительные сведения см. в разделе [Поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).