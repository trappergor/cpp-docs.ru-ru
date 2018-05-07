---
title: Предупреждение компилятора ресурсов RW4004 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94bd1c043ac5660c5cb8fc8b2bfa1dd2f6968b55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-warning-rw4004"></a>Предупреждение компилятора ресурсов RW4004
Символ ASCII не соответствует виртуальному коду клавиши.  
  
 Строковый литерал был использован для виртуального кода клавиши в акселераторе VIRTKEY.  
  
 Это предупреждение позволяет продолжить работу, но имейте в виду, что созданные сочетания клавиш могут не соответствовать указанной строке. (акселераторы VIRTKEY используют другие коды клавиш, чем акселераторы ASCII).  
  
 Если строковые литералы являются синтаксически правильными, вы можете только обеспечить получение нужных с помощью сочетаний клавиш **VK_\* #define** в WINDOWS.h.