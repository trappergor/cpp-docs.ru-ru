---
title: "Предупреждение (уровень 3) C4622 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4622
dev_langs: C++
helpviewer_keywords: C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52f4491d26cfa56f48ed479b30daeafe9cc01adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4622"></a>Предупреждение компилятора (уровень 3) C4622
перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"  
  
 Информация CodeView в указанном файле была утеряна при выполнении компиляции с параметром [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (использование предкомпилированных заголовков).  
  
 Переименуйте объектный файл (с использованием параметра [/Fo](../../build/reference/fo-object-file-name.md)) при создании или использовании файла предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.