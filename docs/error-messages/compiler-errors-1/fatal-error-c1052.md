---
title: "Неустранимая ошибка C1052 | Документы Microsoft"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f3ab91c1c79b822a4d9a33fb0ab5fbd88146fff0
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="fatal-error-c1052"></a>Неустранимая ошибка C1052
файл базы данных программы, "*filename*", был сформирован компоновщиком с/debug: fastlink; компилятор не может обновить такой PDB-файл; удалите его или используйте параметр /Fd, чтобы указать другое имя файла PDB-файла  
  
Компилятору не удается обновить те же файлы базы данных (PDB) программы, которые создаются компоновщиком при [/debug: fastlink](../../build/reference/debug-generate-debug-info.md) параметра. Обычно компилятором PDB-файлы и PDB-файлы компоновщиком иметь разные имена. Тем не менее если они настроены для использования с теми же именами, эта ошибка может возникнуть.  
  
Чтобы устранить эту проблему, можно явным образом удалить PDB-файлы перед повторите компиляцию, или можно создать разные имена для создаваемых компилятора и компоновщика PDB-файлы. Чтобы создать другие имена файлов PDB-ФАЙЛ компилятором в командной строке, используйте [/Fd](../../build/reference/fd-program-database-file-name.md) параметр. Чтобы создать другие имена файлов PDB-ФАЙЛ в Интегрированной среде разработки, откройте **страницы свойств** диалогового окна проекта, а в **свойства конфигурации**, **C/C++**, **выходные файлы** задайте **имя файла базы данных программы** свойство. По умолчанию это свойство является `$(IntDir)vc$(PlatformToolsetVersion).pdb`. Кроме того можно задать имя PDB-файла компоновщиком. Откройте **страницы свойств** диалогового окна проекта, а в **свойства конфигурации**, **компоновщика**, **Отладка** задайте **создавать файл базы данных программы** свойство. По умолчанию для свойства задано значение `$(OutDir)$(TargetName).pdb`.  

