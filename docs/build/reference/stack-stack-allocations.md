---
title: "Параметр /STACK (выделение памяти в стеке) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.StackReserveSize"
  - "VC.Project.VCLinkerTool.StackCommitSize"
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Параметр компоновщика STACK"
  - "Параметр компоновщика -STACK"
  - "выделение памяти, стек"
  - "Параметр компоновщика /STACK"
  - "стек, установка размера"
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметр /STACK (выделение памяти в стеке)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Заметки  
 Параметр \/STACK задает размер стека в байтах.  Этот параметр следует использовать только при построении исполняемого файла.  
  
 Значение `reserve` определяет общий объем выделяемой памяти стека в виртуальной памяти.  Для ARM x86 и компьютеры [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], размер стека по умолчанию — 1 МБ.  
  
 Значение параметра `commit` интерпретируется операционной системой.  В Windows WindowsRT он определяет объем физической памяти для выделения одновременно.  Выделенная виртуальная память резервирует пространство в файле разбиения по страницам.  Более высокое `commit` значение позволяет сэкономить время, когда приложению требуется большее пространство стека, но увеличивает требования к памяти и по возможности времени запуска.  Для ARM x86 и компьютеры [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], фиксация значение по умолчанию 4 КБ.  
  
 Укажите значения `reserve` и `commit` в нотации десятичного числа или языка C\#.  
  
 Также можно задать объем стека с помощью оператора [STACKSIZE](../../build/reference/stacksize.md) в файле определения модуля с расширением DEF.  В случае одновременного указания параметр **STACKSIZE** переопределяет значение параметра \/STACK.  Чтобы изменить объем стека после построения исполняемого файла, используйте программу [EDITBIN](../Topic/EDITBIN%20Reference.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените значение одного из следующих свойств:  
  
    -   **Выделить память для стека**  
  
    -   **Резервируемый размер стека**  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)