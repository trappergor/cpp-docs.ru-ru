---
title: "/doc (обработка комментариев документации) (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "/doc"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/doc - параметр компилятора [C++]"
  - "комментарии, в коде C++"
  - "-doc - параметр компилятора [C++]"
  - "документация XML, комментарии в исходных файлах"
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /doc (обработка комментариев документации) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает компилятор, чтобы обработать комментарии документации в файлах источника кода, и создает XDC\-файл для каждого файла с исходным кодом, в котором есть комментарии к документации.  
  
## Синтаксис  
  
```  
/doc[name]  
```  
  
## Аргументы  
 `name`  
 Имя XDC\-файла, который будет создан компилятором.  Только корректный CPP\-файл передается для компиляции.  
  
## Заметки  
 XDC\-файлы выполняются в XML\-файле при помощи xdcmake.exe.  Для получения дополнительной информации см. [Справочник по XDCMake](../../ide/xdcmake-reference.md).  
  
 Можно добавить комментарии документации в файл с исходным кодом.  Для получения дополнительной информации см. [Рекомендуемые теги для комментариев документации](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md).  
  
 Параметр **\/doc** несовместим с параметром **\/clr:oldSyntax**.  Дополнительные сведения см. в разделе [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Чтобы использовать созданный XML\-файл с помощью функции IntelliSense, имя XML\-файла должно совпадать с именем сборки, а сам XML\-файл должен находиться в одном каталоге со сборкой.  Таким образом, если в проект Visual Studio добавляется ссылка на сборку, то XML\-файл также будет найден.  Дополнительные сведения см. в разделах [Использование технологии IntelliSense](../Topic/Using%20IntelliSense.md) и [Создание XML\-примечаний к коду](../Topic/Supplying%20XML%20Code%20Comments.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **C\/C\+\+**.  
  
4.  Щелкните страницу свойств **Выходные файлы**.  
  
5.  Измените свойство **Создать файлы XML\-документации**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)