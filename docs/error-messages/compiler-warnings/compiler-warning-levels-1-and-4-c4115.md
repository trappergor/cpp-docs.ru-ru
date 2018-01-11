---
title: "Предупреждение (уровни 1 и 4) C4115 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4115
dev_langs: C++
helpviewer_keywords: C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec1c4377c2b7670b9d934d13d09bc5336fe5f30b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Предупреждение компилятора (уровни 1 и 4) C4115
"тип": определение именованного типа в круглых скобках  
  
 Указанный символ используется для определения структуры, объединения или перечисляемого типа в выражении в скобках. Область определения может быть непредусмотренной.  
  
 В вызове функции C определение имеет глобальную область. В вызове C++ определение имеет ту же область, что и вызываемая функция.  
  
 Это предупреждение также может быть вызвано деклараторами внутри скобок (такими как прототипы), которые не являются выражениями в скобках.  
  
 Это предупреждение уровня 1 для программ C++ и программ C, скомпилированных в режиме совместимости с ANSI (/Za). В противном случае оно имеет уровень 3.