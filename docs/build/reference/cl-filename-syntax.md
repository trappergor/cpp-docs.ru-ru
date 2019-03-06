---
title: Синтаксис имен файлов CL
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: d2dd51370fd346c4cd7dad7bb97bfa76a9f759d9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420730"
---
# <a name="cl-filename-syntax"></a>Синтаксис имен файлов CL

CL принимает файлы, имена которых соответствуют соглашениям об именовании файлов для файловых систем FAT, HPFS или NTFS. Любое имя файла может включать полный или частичный путь. Полный путь содержит букву диска и одно или несколько имен папок. CL принимает имена файлов с разделением обратной косой черты (\\) или косой черты (/). Имена файлов, содержащие пробел, должны быть заключены в двойные кавычки. В частичном имени файла не указывается буква диска; подразумевается, что нужно использовать текущий диск. Если путь не указан, то подразумевается, что файл находится в текущей папке.

Расширение файла определяет, каким образом обрабатывается файл. Файлы C и C++ с расширениями .c, .cxx и .cpp компилируются. Другие файлы, в том числе файлы с расширением .obj, библиотеки (.lib) и файлы определений модулей (.def) передаются в компоновщик без обработки.

## <a name="see-also"></a>См. также

[Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)
