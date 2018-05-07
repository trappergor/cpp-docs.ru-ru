---
title: Математическая ошибка M6111 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b03937ed442b169b960d573b44c0eb6ebca9660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6111"></a>Математическая ошибка M6111
потеря значимости в стеке  
  
 Операции с плавающей точкой привело к нижнюю границу стек на 8087/287/387 или эмуляторе.  
  
 Эта ошибка часто возникает при вызове `long double` функцию, которая не возвращает значение. Например следующие приводит к возникновению ошибки после компиляции и запуска:  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Программа завершается с кодом завершения 139.