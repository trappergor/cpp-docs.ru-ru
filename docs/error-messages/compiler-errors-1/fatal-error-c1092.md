---
title: "Неустранимая ошибка C1092 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
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
ms.openlocfilehash: 6d93fd662b638126e21d5f5f034138c0e6f0e0ad
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1092"></a>Неустранимая ошибка C1092
Режим "Изменить и продолжить" не поддерживает изменения типов данных; требуется сборка  
  
 Был изменен или добавлен тип данных с момента последнего успешного построения.  
  
-   Изменить и продолжить не поддерживает изменения существующих типов данных, включая определения класса, структуры или перечисления. Необходимо остановить отладку и собрать приложение.  
  
-   Изменить и продолжить не поддерживает добавление новых типов данных, если файл базы данных программы, такие как vc*x*0. pdb (где *x* – основная используемая версия Visual C++) доступен только для чтения. Чтобы добавить типы данных, компилятор необходимо открыть PDB-файл в режиме записи.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Устранение этой ошибки без завершения текущего сеанса отладки  
  
1.  Верните тип данных в его состояние до ошибки.  
  
2.  В меню **Отладка** выберите команду **Применить изменения кода**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Устранение этой ошибки без изменения исходного кода  
  
1.  В меню **Отладка** выберите **Остановить отладку**.  
  
2.  В меню **Сборка** выберите **Сборка**.  
  
 Дополнительные сведения см. в разделе [поддерживаемые изменения кода](/visualstudio/debugger/supported-code-changes-cpp).
