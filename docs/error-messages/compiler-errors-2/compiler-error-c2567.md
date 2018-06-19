---
title: Ошибка компилятора C2567 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05f89362f36a6ba576e9829153f0d8931c4975c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229693"
---
# <a name="compiler-error-c2567"></a>Ошибка компилятора C2567
не удается открыть метаданные в «файл», файл может удален или перемещен  
  
 Файл метаданных, на который была ссылка в источнике (с `#using`) не найден в том же каталоге процессом компилятора серверной части, которая была процессом компилятора переднего плана. В разделе [# директива using](../../preprocessor/hash-using-directive-cpp.md) для получения дополнительной информации.  
  
 C2567 может возникать, если компиляция выполняется с **/c** на одном компьютере и затем попытка создания кода во время компоновки на другом компьютере. Дополнительные сведения см. в разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Кроме того, это может указывать на нехватку памяти.  
  
 Чтобы исправить эту ошибку, убедитесь, что является файл метаданных в той же папке каталогов для всех этапов процесса построения.