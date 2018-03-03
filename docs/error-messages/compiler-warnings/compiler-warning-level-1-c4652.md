---
title: "Предупреждение (уровень 1) C4652 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4652
dev_langs:
- C++
helpviewer_keywords:
- C4652
ms.assetid: 2cf2c666-8cdd-4dd9-bda0-662921498b03
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce687d0581b5f8b72ba73009e61a4fcf8e5cde93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4652"></a>Предупреждение компилятора (уровень 1) C4652
параметр компилятора «параметр» несовместим с предкомпилированным заголовком; текущий параметр командной строки переопределяет параметр, определенный в заголовке  
  
 Указанный параметр командной строки отличается от использованного при создании предкомпилированного заголовка (.pch). Использовался параметр, указанный в текущей командной строки.  
  
 Это предупреждение можно избежать, повторное создание предкомпилированного заголовка с указанный параметр командной строки.