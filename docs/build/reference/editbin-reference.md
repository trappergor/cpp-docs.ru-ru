---
title: Справочник ЕDITBIN | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0ff9c0c58498361764dcc1b6c454c9b629d9bed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="editbin-reference"></a>Справочник ЕDITBIN
Двоичный редактор файла COFF корпорации Майкрософт (программа EDITBIN. (EXE) изменяет двоичные файлы общих объекта файла формат COFF. EDITBIN можно использовать для изменения объектных файлов, исполняемых файлов и библиотек динамической компоновки (DLL).  
  
> [!NOTE]
>  Это средство можно запустить только из командной строки [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. В системной командной строке или проводнике это невозможно.  
  
 EDITBIN не доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора. Изменения в двоичные файлы, созданные с параметром /GL будет осуществляться через компиляцию и компоновку.  
  
-   [Командная строка EDITBIN](../../build/reference/editbin-command-line.md)  
  
-   [Параметры EDITBIN](../../build/reference/editbin-options.md)  
  
## <a name="see-also"></a>См. также  
 [Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)