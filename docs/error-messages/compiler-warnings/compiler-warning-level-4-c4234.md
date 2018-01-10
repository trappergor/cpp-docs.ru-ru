---
title: "Предупреждение (уровень 4) C4234 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4234
dev_langs: C++
helpviewer_keywords: C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68f4b2c3b51caf5e0438c2ead293823885b73157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4234"></a>Предупреждение компилятора (уровень 4) C4234
использовано нестандартное расширение: «ключевое слово» зарезервировано для будущего использования  
  
 Компилятор еще не реализует используемое ключевое слово.  
  
 Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например, чтобы сделать C4234 в предупреждение уровня 4,  
  
```  
#pragma warning(2:4234)  
```  
  
 в файле исходного кода.