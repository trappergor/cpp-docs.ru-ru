---
title: "Ошибка компилятора C2567 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 4
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6cd355d7654f931196acc324f7d58b99c6f25f29
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2567"></a>Ошибка компилятора C2567
не удалось открыть метаданные в «файл», файл может перемещены или удалены  
  
 Файл метаданных, который упоминается в источнике (с `#using`) не найден в том же каталоге процессом серверной части компилятора, которая была процессом компилятора переднего плана. В разделе [# директива using](../../preprocessor/hash-using-directive-cpp.md) подробнее.  
  
 C2567 может возникать, если компиляция выполняется с **/c** на одном компьютере и затем попытка создания кода во время компоновки на другом компьютере. Дополнительные сведения см. в разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Он также может указывать на нехватку памяти.  
  
 Чтобы исправить эту ошибку, убедитесь, что является файл метаданных в том же расположении каталога для всех этапов процесса построения.
