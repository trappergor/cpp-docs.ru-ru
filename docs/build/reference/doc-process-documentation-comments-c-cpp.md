---
title: -doc (обработка комментариев документации) (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 899ff6b774c365ce9df3019ef5ba6d08d0d7b93d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371285"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (обработка комментариев документации) (C/C++)
Указывает компилятору на необходимость обработать комментарии документации в файлах исходного кода и создания XDC-файл для каждого файла исходного кода с комментариями документации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>Аргументы  
 `name`  
 Имя XDC-файл, компилятор создаст. Действительно только когда CPP-файл передается в компиляцию.  
  
## <a name="remarks"></a>Примечания  
 В XML-файл с xdcmake.exe обрабатываются XDC-файлах. Дополнительные сведения см. в разделе [Справочник по XDCMake](../../ide/xdcmake-reference.md).  
  
 Можно добавить комментарии к документации в файлах исходного кода. Дополнительные сведения см. в разделе [Рекомендуемые теги для комментариев документации](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 Чтобы использовать созданный XML-файл с поддержкой технологии IntelliSense, сделайте имя файла XML-файла, таким же, как сборка, которую требуется поддерживать и поместить XML-файл находится в том же каталоге, что и сборка. При ссылке на сборку в проекте Visual Studio также находится XML-файл. Дополнительные сведения см. в разделе [использование IntelliSense](/visualstudio/ide/using-intellisense) и [Создание примечаний к коду XML](/visualstudio/ide/supplying-xml-code-comments).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **C/C++** узла.  
  
4.  Выберите **выходные файлы** страницу свойств.  
  
5.  Изменить **создавать файлы XML-документации** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)