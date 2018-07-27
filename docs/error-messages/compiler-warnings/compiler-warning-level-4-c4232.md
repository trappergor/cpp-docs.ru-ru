---
title: Предупреждение (уровень 4) C4232 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 093f9eeeb27b402b58f3d53ae34952c34dca3779
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293832"
---
# <a name="compiler-warning-level-4-c4232"></a>Предупреждение компилятора (уровень 4) C4232
использовано нестандартное расширение: «идентификатор»: адрес dllimport «dllimport» не является статическим, идентичность не гарантируется  
  
 При использовании расширений Майкрософт (/Ze) можно передать нестатическое значение как адрес функции объявлены с **dllimport** модификатор. В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), это приводит к ошибке.  
  
 Следующий пример приводит к возникновению ошибки C4232:  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```