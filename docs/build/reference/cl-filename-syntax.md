---
title: "Синтаксис имен файлов CL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc9ce614cb67bef1904e8dc464402f362b0cbde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cl-filename-syntax"></a>Синтаксис имен файлов CL
CL принимает файлы, имена которых соответствуют соглашениям об именовании файлов для файловых систем FAT, HPFS или NTFS. Любое имя файла может включать полный или частичный путь. Полный путь содержит букву диска и одно или несколько имен папок. CL принимает имена файлов с разделением обратной косой черты (\\) или косой черты (/). Имена файлов, содержащие пробел, должны быть заключены в двойные кавычки. В частичном имени файла не указывается буква диска; подразумевается, что нужно использовать текущий диск. Если путь не указан, то подразумевается, что файл находится в текущей папке.  
  
 Расширение файла определяет, каким образом обрабатывается файл. Файлы C и C++ с расширениями .c, .cxx и .cpp компилируются. Другие файлы, в том числе файлы с расширением .obj, библиотеки (.lib) и файлы определений модулей (.def) передаются в компоновщик без обработки.  
  
## <a name="see-also"></a>См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)