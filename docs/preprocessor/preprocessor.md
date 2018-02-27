---
title: "Препроцессор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75caab67343e7806e1dd97fb673114949c68a94c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor"></a>Препроцессор
Препроцессор — это текстовый процессор, управляющий текстом файла исходного кода в ходе первого этапа трансляции. Препроцессор не производит синтаксического анализа текста исходного кода, но разбивает его на токены для обнаружения вызовов макросов. Хотя компилятор обычно вызывает препроцессор при первом проходе, препроцессор можно также вызвать отдельно для обработки текста без его компиляции.  
  
 Справочные материалы по препроцессору содержат следующие разделы:  
  
-   [Директивы препроцессора](../preprocessor/preprocessor-directives.md)  
  
-   [Операторы препроцессора](../preprocessor/preprocessor-operators.md)  
  
-   [Предустановленные макросы](../preprocessor/predefined-macros.md)  
  
-   [Директивы pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Листинг исходного кода после предварительной обработки с помощью можно получить [/E](../build/reference/e-preprocess-to-stdout.md) или [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) параметр компилятора. Оба параметра вызывают препроцессор и выводят получающийся текст на стандартное устройство вывода — в большинстве случаев это консоль. Различие заключается в том, что параметр /E сохраняет директивы `#line`, в то время как параметр /EP удаляет эти директивы.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
##  <a name="_predir_special_terminology"></a> Специальная терминология  
 В документации препроцессора термин "аргумент" означает сущность, передаваемую в функцию. В некоторых случаях используются модификаторы "фактический" или "формальный", которые описывают выражение аргумента в вызове функции и объявление аргумента в определении функции, соответственно.  
  
 Термин "переменная" обозначает простой объект данных C-типа. Под термином "объект" понимаются как объекты, так и переменные C++; это собирательный термин.  
  
## <a name="see-also"></a>См. также  
 [Справочник по препроцессору C/C++](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Фазы трансляции](../preprocessor/phases-of-translation.md)