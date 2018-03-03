---
title: "Построение библиотеки импорта и файла экспорта | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 979e052147f058e6c46a1c10b1dd89cfd36ee362
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="building-an-import-library-and-export-file"></a>Построение библиотеки импорта и файла экспорта
Построение библиотеки импорта и экспорта файла, используйте следующий синтаксис:  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 Если указан параметр/DEF, LIB создает выходные файлы из спецификации экспорта, которые передаются в команде LIB. Существует три метода для указания экспортов в рекомендуемом порядке использования:  
  
1.  Объект **__declspec(dllexport)** определение в одном из *объектных* или *библиотеки*  
  
2.  Спецификации/Export:*имя* в командной строке LIB  
  
3.  Определение в **ЭКСПОРТОВ** инструкции`deffile`  
  
 Это те же методы, используемые для указания экспортов при компоновке экспортирующей программы. Программа может использовать более одного метода. Можно указывать части команды LIB (например, несколько *объектных* или спецификации/export) в файле команд в команде LIB, подобно тому, как можно в команде LINK.  
  
 Следующие параметры применяются к сборке библиотеки импорта и экспорта файла:  
  
 / OUT: *импорта*  
 Переопределяет имя выходного файла по умолчанию для *импорта* создаваемой библиотеки. Если/out не указан, по умолчанию называется базовое имя первого файла объекта или библиотеки в команде LIB и расширением. lib. Получает такое же базовое имя библиотеки импорта и расширение файла экспорта. exp.  
  
 / EXPORT: *имя*[= *внутреннееимя*] [, @ `ordinal`[, **NONAME**]] [, **данные**]  
 Экспортирует функцию из программы, чтобы разрешить другие программы для вызова функции. Также можно экспортировать данные (с помощью **данные** ключевое слово). Экспорт обычно определяется в библиотеке DLL.  
  
 *Имя* является имя элемента данных или функции, как он будет использоваться вызывающей программой. Кроме того, можно указать *внутреннееимя* как функции, известной определяющей программе; по умолчанию *внутреннееимя* совпадает со значением *имя*. `ordinal` Задает индекс в таблице экспорта в диапазоне от 1 до 65 535; Если вы не укажете `ordinal`, LIB назначает один. **NONAME** ключевое слово экспортирует функцию только по порядковому номеру, без *имя*. **Данные** ключевое слово используется для экспорта только для данных объектов.  
  
 / INCLUDE:`symbol`  
 Добавляет указанный символ в таблицу символов. Этот параметр полезен для принудительного применения объект библиотеки, в противном случае не будет включен.  
  
 Обратите внимание, что при создании библиотеки импорта в предварительном этапе перед созданием DLL-файла, вам необходимо использовать тот же набор объектных файлов при построении DLL-файл, как пройденный при сборке библиотеки импорта.  
  
## <a name="see-also"></a>См. также  
 [Работа с библиотеками импорта и файлами экспорта](../../build/reference/working-with-import-libraries-and-export-files.md)