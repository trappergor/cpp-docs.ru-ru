---
title: "-Fe (именование EXE-файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d74892ef670ed53e68701730fdb71554989a495c
ms.sourcegitcommit: d24de38f9da844f824acb9d200a3f263077145fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="fe-name-exe-file"></a>/Fe (именование EXE-файла)

Указывает имя и каталог для файла .exe или библиотеку DLL, созданную компилятором.

## <a name="syntax"></a>Синтаксис

> **/Fe**[_pathname_]  
> **/Fe:** _pathname_  

### <a name="arguments"></a>Аргументы

*pathname*<br/>
Абсолютный или относительный путь и имя базового файла или относительный или абсолютный путь к каталогу или базовое имя файла для создаваемого исполняемого файла.

## <a name="remarks"></a>Примечания

**/Fe** позволяет указать в выходной каталог, имя выполняемого файла или оба для создаваемого исполняемого файла. Если *pathname* заканчивается на разделитель пути (**&#92;**), предполагается, чтобы указать выходной каталог. В противном случае — последний компонент *pathname* используется как базовое имя выходного файла, а остальная часть *pathname* задает выходной каталог. Если *pathname* не имеет каких-либо разделителей пути предполагалось, чтобы указать имя выходного файла в текущем каталоге. *Pathname* должны заключаться в двойные кавычки (**»**), если он содержит символы, не может быть в короткий путь, например пробелы, расширенных символов и компоненты пути более восьми символов долго.

Когда **/Fe** параметр не указан, или при создании базового файла имя не указано в *pathname*, компилятор придает выходному файлу имя по умолчанию базовое имя первого файла источника или объекта, заданного с помощью в командной строке и расширением .exe или .dll.

При указании [/c (компиляция без связывания)](c-compile-without-linking.md) параметр **/Fe** не делает ничего.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте **свойства конфигурации** > **компоновщика** > **Общие** страницу свойств.

1. Изменить **выходной файл** свойство. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Пример

Следующая команда компилирует и связывает все исходные файлы C в текущем каталоге. Полученный исполняемый файл с именем PROCESS.exe и создается в каталоге «Project\bin Name\repos\My C:\Users\User».

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Пример

Следующая команда создает исполняемый файл в `C:\BIN` с тем же базовым именем, что и первый исходный файл в текущем каталоге:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](../../build/reference/output-file-f-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Указание пути](../../build/reference/specifying-the-pathname.md)<br/>
