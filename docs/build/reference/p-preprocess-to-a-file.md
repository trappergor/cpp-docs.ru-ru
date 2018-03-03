---
title: "-P (Предварительная обработка файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs:
- C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f4de2f19820a846197806e0a24ddc213dd636c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="p-preprocess-to-a-file"></a>/P (вывод результатов предварительной обработки в файл)
Выполняет предварительную обработку клавиатурных исходными файлами C и C++ и записывает предварительно обработанные выходные данные в файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/P  
```  
  
## <a name="remarks"></a>Примечания  
 Файл имеет такое же базовое имя исходного файла и расширение i. В процессе выполняются все директивы препроцессора, расширения макросов и удаляются комментарии. Чтобы сохранить комментарии в предварительно обработанные выходные данные, используйте [/C (сохранять комментарии во время предварительной обработки)](../../build/reference/c-preserve-comments-during-preprocessing.md) вместе с **/P**.  
  
 **/P** добавляет `#line` директивы в выходные данные в начале и в конце каждого включенного файла, а также вокруг строк, удаленных директивами препроцессора для условной компиляции. Эти директивы перенумерации строк предварительно обработанного файла. В результате ошибки, созданные более поздних этапах обработки, ссылаются на номера строк исходного файла, а не строк предварительно обработанного файла. Для подавления создания `#line` использование директив, [/EP (Предварительная обработка в поток стандартных выходных файлов без директив #line)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) и **/P**.  
  
 **/P** параметр отменяет компиляцию. Не создает OBJ-файл, даже если вы используете [/Fo (имя объектного файла)](../../build/reference/fo-object-file-name.md). Необходимо повторить отправку предварительно обработанного файла для компиляции. **/P** также подавляются выходных файлов из **/FA**, **/Fa**, и **/Fm** параметры. Дополнительные сведения см. в разделе [/FA /Fa (файл со списком)](../../build/reference/fa-fa-listing-file.md) и [/Fm (имя файла сопоставления)](../../build/reference/fm-name-mapfile.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **препроцессор** страницу свойств.  
  
4.  Изменить **Создание предварительно обработанного файла** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Пример  
 Следующая командная строка выполняет предварительную обработку клавиатурных `ADD.C`, сохраняет комментарии, добавляет `#line` директив и записывает результаты в файл `ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/Fi (Предварительная обработка имени выходного файла)](../../build/reference/fi-preprocess-output-file-name.md)