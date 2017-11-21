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
ms.openlocfilehash: 86a44dfc09e3b0bcb0744115ce4ddfaf8d96f258
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4234"></a>Предупреждение компилятора (уровень 4) C4234
использовано нестандартное расширение: «ключевое слово» зарезервировано для будущего использования  
  
 Компилятор еще не реализует используемое ключевое слово.  
  
 Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например, чтобы сделать C4234 в предупреждение уровня 4,  
  
```  
#pragma warning(2:4234)  
```  
  
 в файле исходного кода.