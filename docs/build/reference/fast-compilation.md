---
title: Быстрая компиляция | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- compilation, performance
- cl.exe compiler, performance
- fast compiling
ms.assetid: 5fead136-ba69-40c8-8e25-236f89d5990a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5d29ea4684e5f29374f11cf75dec94756ddde84
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fast-compilation"></a>Быстрая компиляция
Для увеличения скорости компиляции:  
  
-   Используйте [минимального перепостроения](../../build/reference/gm-enable-minimal-rebuild.md), в котором компилятор C++ повторных компиляций исходного файла только в том случае, если он зависит от изменений класса в файле заголовка.  
  
-   [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md) и использовать [предкомпилированный заголовок параметры](../../build/reference/yc-create-precompiled-header-file.md).  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)