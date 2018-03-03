---
title: "Предупреждение компилятора ресурсов RW4004 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0249f7d01ee344f0fa17bdc39e58e9fce26c9b25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rw4004"></a>Предупреждение компилятора ресурсов RW4004
Символ ASCII не соответствует виртуальному коду клавиши.  
  
 Строковый литерал был использован для виртуального кода клавиши в акселераторе VIRTKEY.  
  
 Это предупреждение позволяет продолжить работу, но имейте в виду, что созданные сочетания клавиш могут не соответствовать указанной строке. (акселераторы VIRTKEY используют другие коды клавиш, чем акселераторы ASCII).  
  
 Если строковые литералы являются синтаксически правильными, вы можете только обеспечить получение нужных с помощью сочетаний клавиш **VK_\* #define** в WINDOWS.h.