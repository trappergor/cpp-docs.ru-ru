---
title: "Быстрая компиляция | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- performance, cle.exe compiler
- compilation, performance
- cl.exe compiler, performance
- fast compiling
ms.assetid: 5fead136-ba69-40c8-8e25-236f89d5990a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 917e098b25865daabc65bf70a01a8539a0d5c79b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fast-compilation"></a>Быстрая компиляция
Для увеличения скорости компиляции:  
  
-   Используйте [минимального перепостроения](../../build/reference/gm-enable-minimal-rebuild.md), в котором компилятор C++ повторных компиляций исходного файла только в том случае, если он зависит от изменений класса в файле заголовка.  
  
-   [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md) и использовать [предкомпилированный заголовок параметры](../../build/reference/yc-create-precompiled-header-file.md).  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)