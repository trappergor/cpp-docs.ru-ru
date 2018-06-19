---
title: '-EP (Предварительная обработка в поток стандартных выходных файлов без директив #line) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
dev_langs:
- C++
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38047fecbbd1bbaa87db3766b046efa8b446d93a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375387"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (предварительная обработка в поток стандартных выходных файлов без директив #line)
Выполняет предварительную обработку клавиатурных исходными файлами C и C++ и копирование предварительно обработанных файлов на стандартное устройство вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/EP  
```  
  
## <a name="remarks"></a>Примечания  
 В процессе выполняются все директивы препроцессора, расширения макросов и удаляются комментарии. Чтобы сохранить комментарии в предварительно обработанные выходные данные, используйте [/C (сохранять комментарии во время предварительной обработки)](../../build/reference/c-preserve-comments-during-preprocessing.md) вариант с **/EP**.  
  
 **/EP** параметр отменяет компиляцию. Необходимо повторить отправку предварительно обработанного файла для компиляции. **/EP** также подавляются выходных файлов из **/FA**, **/Fa**, и **/Fm** параметры. Дополнительные сведения см. в разделе [/FA /Fa (файл со списком)](../../build/reference/fa-fa-listing-file.md) и [/Fm (имя файла сопоставления)](../../build/reference/fm-name-mapfile.md).  
  
 Ошибки, созданные в более поздних этапах обработки, ссылаются на номера строк предварительно обработанного файла, а не исходный файл. Номера строк для ссылки на исходный файл, используйте [/E (Предварительная обработка до stdout)](../../build/reference/e-preprocess-to-stdout.md) вместо него. **/E** добавляет параметр `#line` директивы в выходные данные для этой цели.  
  
 Для отправки предварительно обработанные выходные данные с `#line` директив, в файл используйте [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) вместо него.  
  
 Для отправки предварительно обработанные выходные данные в stdout, с `#line` использование директив, **/P** и **/EP** друг с другом.  
  
 Нельзя использовать предкомпилированные заголовки с **/EP** параметр.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **препроцессор** страницу свойств.  
  
4.  Изменить **Создание предварительно обработанного файла** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Пример  
 Следующая командная строка выполняет предварительную обработку файла `ADD.C`, сохраняет комментарии и выводит результат на стандартное устройство вывода:  
  
```  
CL /EP /C ADD.C  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)