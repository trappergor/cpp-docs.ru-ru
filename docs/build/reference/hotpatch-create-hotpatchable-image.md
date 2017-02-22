---
title: "/hotpatch (Создать образ с обновлениями) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/hotpatch"
  - "VC.Project.VCCLCompilerTool.CreateHotpatchableImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "критическое обновление"
  - "-hotpatch - параметр компилятора [C++]"
  - "/hotpatch - параметр компилятора [C++]"
  - "критическое обновление"
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /hotpatch (Создать образ с обновлениями)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Подготавливает образ к горячему обновлению.  
  
## Синтаксис  
  
```  
/hotpatch  
```  
  
## Заметки  
 При **\/hotpatch** используется в компиляции, компилятор гарантирует, что первая инструкция каждой функции по крайней мере 2 байта, которая должна быть высоким для внесения исправлений.  
  
 Для выполнения подготовки для создания образа hotpatchable после использования **\/hotpatch** компилироваться, необходимо использовать [\/FUNCTIONPADMIN \(создание образа, допускающего горячее обновление\)](../../build/reference/functionpadmin-create-hotpatchable-image.md) для связывания.  При компилировать и связать изображение с помощью одного вызова cl.exe, **\/hotpatch** подразумевает **\/functionpadmin**.  
  
 Так как инструкции всегда больше или равен 2 байт на архитектуру ARM, а поскольку x64 компиляция всегда выполняется при **\/hotpatch** задано, нет необходимости указывать **\/hotpatch** при компилировать для этих целевых объектов; однако по\-прежнему необходимо связать с помощью **\/functionpadmin** для создания hotpatchable образы для них.  Параметр компилятора **\/hotpatch** влияет только на компиляцию x86.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Добавьте параметр компилятора в окно **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Руководство  
 Управление обновлениями Дополнительные сведения о см. в разделе «инструкции по безопасности для управления обновлениями» в [http:\/\/www.microsoft.com\/technet\/security\/guidance\/PatchManagement.mspx](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)