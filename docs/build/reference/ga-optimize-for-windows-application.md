---
title: "/GA (Оптимизация для приложений Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA - параметр компилятора [C++]"
  - "GA - параметр компилятора [C++]"
  - "-GA - параметр компилятора [C++]"
  - "Оптимизация для параметров компилятора Windows"
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /GA (Оптимизация для приложений Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получение большей эффективности кода для EXE\-файла для доступа к переменным локальной памяти потока.  
  
## Синтаксис  
  
```  
/GA  
```  
  
## Заметки  
 **\/GA** скорость доступа к данным объявлена с помощью [\_\_declspec\(thread\)](../../cpp/declspec.md) в программе для Windows.  Когда этот параметр установлен, макрос [\_\_tls\_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) предполагается равным 0.  
  
 Использование **\/GA** для библиотеки DLL может привести к недопустимой генерации кода.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)