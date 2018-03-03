---
title: "Предупреждение (уровень 4) C4092 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4092
dev_langs:
- C++
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6eec21584ec56567b818f23e7dfcf5fb708369ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4092"></a>Компилятор C4092 предупреждение (уровень 4)
Возвращает «long без знака» sizeof  
  
 Операнд `sizeof` оператор имеет очень большой размер, поэтому `sizeof` вернул unsigned **длинные**. Это предупреждение возникает при использовании расширений Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). В режиме совместимости с ANSI (/Za) результат усекается вместо него.