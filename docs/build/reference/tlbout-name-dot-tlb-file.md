---
title: "/TLBOUT (задание имени TLB-файла) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TypeLibraryFile"
  - "/tlbout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TLB-файлы, переименование"
  - "/TLBOUT - параметр компоновщика"
  - "TLB-файлы, переименование"
  - "TLBOUT - параметр компоновщика"
  - "-TLBOUT - параметр компоновщика"
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBOUT (задание имени TLB-файла)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBOUT:[path\]filename  
```  
  
## Заметки  
 Здесь:  
  
 *путь*  
 Указание относительного или абсолютного пути, по которому должен быть создан TLB\-файл.  
  
 *filename*  
 Указывает имя файла TLB, создаваемого компилятором MIDL.  Предположения о расширении файла не выносятся. Укажите *filename*.tlb, если требуется расширение TLB.  
  
## Заметки  
 Параметр \/TLBOUT задает имя и расширение TLB\-файла.  
  
 Компилятор MIDL вызывается компоновщиком Visual C\+\+ при компоновке проектов, имеющих атрибут [module](../../windows/module-cpp.md).  
  
 Если параметр \/TLBOUT не указан, то TLB\-файл получит имя из параметра [\/IDLOUT](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md) *filename*.  Если параметр \/IDLOUT не указан, то TLB\-файл будет называться vc70.tlb.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Щелкните страницу свойств **Внедренный IDL**.  
  
4.  Измените значение свойства **Библиотека типов**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(не преобразовывать атрибуты в MIDL\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(Указание параметров командной строки MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)