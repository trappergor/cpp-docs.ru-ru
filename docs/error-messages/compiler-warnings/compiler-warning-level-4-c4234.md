---
title: Предупреждение (уровень 4) C4234 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4234
dev_langs:
- C++
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8d5b7a2999b77c0b34ee925f5dd85a0a27c63f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293521"
---
# <a name="compiler-warning-level-4-c4234"></a>Предупреждение компилятора (уровень 4) C4234
использовано нестандартное расширение: «ключевое слово» зарезервировано для будущего использования  
  
 Компилятор еще не реализует используемое ключевое слово.  
  
 Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например, чтобы сделать C4234 в предупреждение уровня 4,  
  
```  
#pragma warning(2:4234)  
```  
  
 в файле исходного кода.