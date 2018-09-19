---
title: Командные файлы LINK | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2611fc0c16e4ff30d7802989518ca8c5d8dc33af
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713734"
---
# <a name="link-command-files"></a>Командные файлы LINK

Аргументы командной строки можно передать ССЫЛКУ в виде командного файла. Чтобы указать командному файлу, который компоновщик, используйте следующий синтаксис:

> **ССЫЛКА \@**  <em>commandfile</em>

*Commandfile* имя текстового файла. Нет пробел или символ табуляции должны разделяться знаком (**\@**) и имя файла. Отсутствует расширение по умолчанию; необходимо указать полное имя файла, включая любое расширение. Нельзя использовать подстановочные знаки. Можно указать абсолютный или относительный путь с именем файла. ССЫЛКА не использует переменную среды для поиска файла.

В файле команд, аргументы могут быть разделены пробелами или знаками табуляции (как и в командной строке) и символом новой строки.

Можно указать часть командной строки или в файле команд. Можно использовать более одного командного файла в команде LINK. СВЯЗЬ принимает входные данные командного файла, как если бы он был указан в этом расположении, в командной строке. Командные файлы не могут быть вложенными. LINK выводит на экран содержимого командные файлы, если не [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) параметра.

## <a name="example"></a>Пример

Следующую команду, чтобы создать библиотеку DLL передает имена файлов объектов и библиотек в отдельных командных файлах и использует файл для спецификации параметра/EXPORTS команд, третий:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)