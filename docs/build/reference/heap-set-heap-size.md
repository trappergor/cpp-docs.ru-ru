---
title: "/HEAP (Установка размера кучи) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.HeapCommitSize"
  - "/heap"
  - "VC.Project.VCLinkerTool.HeapReserveSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HEAP - параметр компоновщика"
  - "выделение кучи, размер кучи - установка"
  - "HEAP - параметр компоновщика"
  - "-HEAP - параметр компоновщика"
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HEAP (Установка размера кучи)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/HEAP:reserve[,commit]  
```  
  
## Заметки  
 Параметр \/HEAP задает размер кучи в байтах.  Этот параметр используется только при сборке EXE\-файлов.  
  
 Аргумент *reserve* задает общее выделение виртуальной памяти для кучи.  Размер кучи по умолчанию составляет 1 МБ.  Компоновщик округляет указанное значение до ближайших 4 байт.  
  
 Необязательный аргумент `commit` интерпретируется операционной системой.  В Windows NT\/Windows 2000 он задает объем физической памяти для единовременного выделения.  Выделенная виртуальная память резервирует пространство в файле разбиения по страницам.  Более высокие значения `commit` позволяют сэкономить время, когда приложению требуется больше пространства для кучи, однако увеличивают требования к памяти и, возможно, время запуска.  
  
 Значения *reserve* и `commit` задаются в нотации в десятичном формате либо в формате языка С.  
  
 Это также можно сделать с помощью файла определения модуля и параметра [HEAPSIZE](../../build/reference/heapsize.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените значение свойства **Выделить память для кучи**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)