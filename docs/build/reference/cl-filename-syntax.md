---
title: Синтаксис имен файлов CL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 121cd8971be65e15ad6445cb347baf478046bf3e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370466"
---
# <a name="cl-filename-syntax"></a>Синтаксис имен файлов CL
CL принимает файлы, имена которых соответствуют соглашениям об именовании файлов для файловых систем FAT, HPFS или NTFS. Любое имя файла может включать полный или частичный путь. Полный путь содержит букву диска и одно или несколько имен папок. CL принимает имена файлов с разделением обратной косой черты (\\) или косой черты (/). Имена файлов, содержащие пробел, должны быть заключены в двойные кавычки. В частичном имени файла не указывается буква диска; подразумевается, что нужно использовать текущий диск. Если путь не указан, то подразумевается, что файл находится в текущей папке.  
  
 Расширение файла определяет, каким образом обрабатывается файл. Файлы C и C++ с расширениями .c, .cxx и .cpp компилируются. Другие файлы, в том числе файлы с расширением .obj, библиотеки (.lib) и файлы определений модулей (.def) передаются в компоновщик без обработки.  
  
## <a name="see-also"></a>См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)