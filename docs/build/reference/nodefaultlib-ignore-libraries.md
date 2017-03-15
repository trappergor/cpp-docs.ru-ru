---
title: "Параметр /NODEFAULTLIB (пропуск библиотек) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames"
  - "/nodefaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NODEFAULTLIB - параметр компоновщика"
  - "библиотеки по умолчанию, удаление"
  - "игнорировать библиотеки - параметр компоновщика"
  - "библиотеки, игнорировать"
  - "NODEFAULTLIB - параметр компоновщика"
  - "-NODEFAULTLIB - параметр компоновщика"
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Параметр /NODEFAULTLIB (пропуск библиотек)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NODEFAULTLIB[:library]   
```  
  
## Заметки  
 Здесь:  
  
 *library*  
 Библиотека, пропускаемая компоновщиком при разрешении внешних ссылок.  
  
## Заметки  
 Параметр \/NODEFAULTLIB предписывает компоновщику удаление одной или нескольких стандартных библиотек из списка, в которой выполняется поиск, при разрешении внешних ссылок.  
  
 Чтобы создать OBJ\-файл, в котором отсутствуют ссылки на используемые по умолчанию библиотеки, используйте параметр [\/Zl \(Опущенное по умолчанию имя библиотеки\)](../../build/reference/zl-omit-default-library-name.md).  
  
 По умолчанию при использовании параметра \/NODEFAULTLIB из списка библиотек, в которых осуществляется поиск при разрешении ссылок, удаляются все используемые по умолчанию библиотеки.  Необязательный параметр *library* используется для удаления из списка только указанных библиотек.  Параметр \/NODEFAULTLIB необходимо указывать для каждой исключаемой библиотеки.  
  
 При разрешении ссылок на внешние определения поиск сначала осуществляется в явно заданных библиотеках, затем в библиотеках по умолчанию, заданных с помощью параметра \/DEFAULTLIB, а затем в библиотеках по умолчанию, определенных в OBJ\-файлах.  
  
 Параметр \/NODEFAULTLIB:*library* переопределяет параметр [\/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*library*, в котором задан такой же параметр *library*.  
  
 Если параметр \/NODEFAULTLIB используется для построения программы без библиотеки времени выполнения C, можно использовать параметр [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) для определения точки \(функции\) входа в программу.  Для получения дополнительной информации см. [Особенности библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Ввод**.  
  
4.  Выберите свойство **Игнорировать все стандартные библиотеки** или задайте список библиотек с помощью свойства **Игнорировать указанную библиотеку**.  Результаты изменения этих свойств отображаются на странице **Командная строка**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)