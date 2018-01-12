---
title: "Командные файлы LINK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e585fb8fa11d4e3ffe8eff842baacb05f109754c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="link-command-files"></a>Командные файлы LINK
Аргументы командной строки можно передать ССЫЛКУ в виде командный файл. Чтобы задать командный файл для компоновщика, используйте следующий синтаксис:  
  
```  
LINK @commandfile  
```  
  
 `commandfile` Имя текстового файла. Нет пробел или символ табуляции разрешено между символа (@) и имя файла. Расширения по умолчанию; не существует необходимо указать полное имя файла, включая любое расширение. Нельзя использовать подстановочные знаки. Можно указать абсолютный или относительный путь с именем файла. СВЯЗЬ не использует переменную среды для поиска файла.  
  
 В файле команд аргументы могут быть разделены пробелами или символами табуляции (как в командной строке) и символом новой строки.  
  
 В командном файле можно указать все или часть командной строки. Можно использовать более одного командного файла в команде LINK. СВЯЗЬ принимает ввод командного файла, как если бы он был указан в этом расположении, в командной строке. Командные файлы не могут быть вложенными. LINK выводит на экран содержимое командных файлов, если не [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) параметра.  
  
## <a name="example"></a>Пример  
 Следующую команду, чтобы построить библиотеку DLL передает имена объектных файлов и библиотек в отдельных командных файлах и использует файл для спецификации параметра/EXPORTS команды на третий:  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)