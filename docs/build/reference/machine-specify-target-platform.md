---
title: "Параметр /MACHINE (определение целевой платформы) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.TargetMachine"
  - "/machine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MACHINE - параметр компоновщика"
  - "MACHINE - параметр компоновщика"
  - "-MACHINE - параметр компоновщика"
  - "файлы сопоставления, создание компоновщика"
  - "конечная платформа"
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Параметр /MACHINE (определение целевой платформы)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## Заметки  
 Параметр \/MACHINE определяет целевую платформу программы.  
  
 Как правило, нет необходимости указывать параметр \/MACHINE.  Тип компьютера выводится программой LINK из OBJ\-файлов.  Однако в некоторых случаях программе LINK не удается определить тип компьютера, в результате чего отображается [ошибка компоновщика LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md).  При возникновении такой ошибки следует задать параметр \/MACHINE.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Дополнительно**.  
  
4.  Измените значение свойства **Конечный компьютер**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)