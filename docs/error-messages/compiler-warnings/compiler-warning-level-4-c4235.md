---
title: Предупреждение компилятора (уровень 4) C4235 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc63640bc58caefa281b9207b9796ffdf387a7a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292546"
---
# <a name="compiler-warning-level-4-c4235"></a>Предупреждение компилятора (уровень 4) C4235
использовано нестандартное расширение: «ключевое слово» данной архитектурой не поддерживается  
  
 Компилятор не поддерживает используемое ключевое слово.  
  
 Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4235 предупреждение уровня 2, используйте следующую строку кода  
  
```  
#pragma warning(2:4235)  
```  
  
 в файле исходного кода.