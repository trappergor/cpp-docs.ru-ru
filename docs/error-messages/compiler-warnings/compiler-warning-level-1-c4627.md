---
title: "Предупреждение (уровень 1) C4627 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66d199b8dede21f94a963113341eb6426f66a807
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4627"></a>Предупреждение компилятора (уровень 1) C4627
"\<идентификатор >": пропущен при поиске использования предкомпилированного заголовка  
  
 При поиске расположения, где используется предкомпилированный заголовок, компилятор обнаружил `#include` директивы  *\<идентификатор >* включаемого файла. Компилятор игнорирует `#include` директивы, но выдает предупреждение **C4627** если предкомпилированный заголовок еще не содержит  *\<идентификатор >* включаемого файла.  
  
## <a name="see-also"></a>См. также  
 [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)