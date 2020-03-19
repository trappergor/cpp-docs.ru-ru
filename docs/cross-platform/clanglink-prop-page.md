---
title: Свойства компоновщика Clang (Android C++)
ms.date: 10/23/2017
ms.assetid: 66e88848-116c-4eb0-bc57-183394d35b57
f1_keywords:
- VC.Project.VCLinkerTool.Clang.OutputFile
- VC.Project.VCLinkerTool.Clang.Soname
- VC.Project.VCLinkerTool.Clang.ShowProgress
- VC.Project.VCLinkerTool.Clang.Version
- VC.Project.VCLinkerTool.Clang.VerboseOutput
- VC.Project.VCLinkerTool.Clang.IncrementalLink
- VC.Project.VCLinkerTool.Clang.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.Clang.AdditionalLibraryDirectories
- VC.Project.VCLinkerTool.Clang.UnresolvedReferences
- VC.Project.VCLinkerTool.Clang.OptimizeForMemory
- VC.Project.VCLinkerTool.Clang.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.Clang.ForceSymbolReferences
- VC.Project.VCLinkerTool.Clang.ForceFileOutput
- VC.Project.VCLinkerTool.Clang.OmitDebuggerSymbolInformation
- VC.Project.VCLinkerTool.Clang.GenerateMapFile
- VC.Project.VCLinkerTool.Clang.Relocation
- VC.Project.VCLinkerTool.Clang.FunctionBinding
- VC.Project.VCLinkerTool.Clang.NoExecStackRequired
- VC.Project.VCLinkerTool.Clang.WholeArchive
- VC.Project.VCLinkerTool.Clang.AdditionalOptionsPage
- VC.Project.VCLinkerTool.Clang.AdditionalDependencies
- VC.Project.VCLinkerTool.Clang.LibraryDependencies
ms.openlocfilehash: 55b944040157d13741b992f4ec66c35d1b117d95
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470253"
---
# <a name="clang-linker-properties-android-c"></a>Свойства компоновщика Clang (Android C++)

| Свойство | Description | Варианты |
|--|--|--|
| Выходной файл | Параметр переопределяет стандартное имя и расположение программы, которую создает компоновщик. (-o) |
| Отображать ход выполнения | Печатает сообщения хода выполнения компоновщика. |
| Версия | Параметр -version сообщает компоновщику о том, что нужно поместить номер версии в заголовок исполняемого файла. |
| Включить подробные выходные данные | Параметр -verbose сообщает компоновщику о том, что нужно вывести подробные сообщения для отладки. |
| Включить инкрементную компоновку | Параметр сообщает компоновщику о том, что нужно включить инкрементную компоновку. |
| Путь поиска общих библиотек | Позволяет пользователю указать путь поиска общих библиотек. |
| Дополнительные каталоги библиотек | Разрешает пользователю переопределять путь окружения библиотеки. (-L folder). |
| Сообщить о неразрешенных ссылках на символы | Этот параметр включен, если включены отчеты о неразрешенных ссылках на символы. |
| Оптимизировать использование памяти | Оптимизация использования памяти путем повторного чтения таблиц символов по мере необходимости. |
| Игнорировать конкретные стандартные библиотеки | Указывает одно или несколько имен пропускаемых библиотек по умолчанию. |
| Принудительно включать ссылки на символы | Принудительный ввод символа в выходной файл в качестве неопределенного символа. |
| Символьная отладочная информация | Символьная отладочная информация из выходного файла. | **Включить все**<br /><br />**Пропустить символы, которые не требуются для обработки перемещения**<br /><br />**Пропустить только символьную отладочную информацию**<br /><br />**Пропустить всю символьную информацию** |
| Упаковка символьной отладочной информации | Удалить символьную отладочную информацию перед упаковкой.  Для отладки используется копия исходного двоичного файла. |
| Имя файла сопоставления | Параметр "Сопоставление" сообщает компоновщику о том, что нужно создать файл сопоставления с именем, указанным пользователем. |
| Отметить переменные как доступные только для чтения после перемещения | Параметр отмечает переменные как доступные только для чтения после перемещения. |
| Включить немедленное связывание функций | Этот параметр отмечает объект для немедленного связывания функций. |
| Требовать исполняемый стек | Этот параметр отмечает выходные данные как не требующие исполняемого стека. |
| Весь архив | Весь архив использует весь код из источников и дополнительных зависимостей. |
| Дополнительные параметры | Дополнительные параметры. |
| Дополнительные зависимости | Указывает дополнительные элементы для добавления в командную строку компоновки. |
| Зависимости библиотеки | Этот параметр позволяет указать дополнительные библиотеки для добавления в командную строку компоновщика. Дополнительные библиотеки добавляются в конец командной строки компоновщика начинаются с *lib* и заканчиваются расширением *. a* или *. so* .  (-lFILE) |
