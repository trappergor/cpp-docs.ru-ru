---
title: "Ошибка компилятора C2567 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1bbdc535f75230da05a92eb0498176da40e918ea
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2567"></a>Ошибка компилятора C2567
не удается открыть метаданные в «файл», файл может удален или перемещен  
  
 Файл метаданных, на который была ссылка в источнике (с `#using`) не найден в том же каталоге процессом компилятора серверной части, которая была процессом компилятора переднего плана. В разделе [# директива using](../../preprocessor/hash-using-directive-cpp.md) для получения дополнительной информации.  
  
 C2567 может возникать, если компиляция выполняется с **/c** на одном компьютере и затем попытка создания кода во время компоновки на другом компьютере. Дополнительные сведения см. в разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Кроме того, это может указывать на нехватку памяти.  
  
 Чтобы исправить эту ошибку, убедитесь, что является файл метаданных в той же папке каталогов для всех этапов процесса построения.
