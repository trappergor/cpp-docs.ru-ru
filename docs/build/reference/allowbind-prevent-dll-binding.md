---
title: "/ALLOWBIND (запретить привязку DLL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.PreventDLLBinding"
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWBIND - параметр компоновщика"
  - "ALLOWBIND - параметр компоновщика"
  - "-ALLOWBIND - параметр компоновщика"
  - "DLL-привязка"
  - "DLL-библиотеки [C++], привязка - запрещение"
  - "DLL-привязка - запрещение"
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND (запретить привязку DLL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALLOWBIND[:NO]  
```  
  
## Заметки  
 Параметр \/ALLOWBIND:NO устанавливает в заголовке библиотеки DLL бит, который указывает программе Bind.exe на то, что привязка образа не допускается.  Если DLL имеет цифровую подпись, привязывать ее не следует \(при привязке цифровая подпись становится недействительной\).  
  
 Существующую библиотеку DLL можно подготовить к использованию функциональности параметра \/ALLOWBIND с помощью параметра [\/ALLOWBIND](../../build/reference/allowbind.md) программы EDITBIN.  
  
### Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Разверните узлы **Свойства конфигурации**, **Компоновщик** и выберите элемент **Командная строка**.  
  
3.  Введите параметр `/ALLOWBIND:NO` в поле **Дополнительные параметры**.  
  
### Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Функция BindImage](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [Функция BindImageEx](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)