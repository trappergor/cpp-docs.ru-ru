---
title: "/FIXED (фиксированный базовый адрес) | Microsoft Docs"
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
  - "/fixed"
  - "VC.Project.VCLinkerTool.FixedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FIXED - параметр компоновщика"
  - "FIXED - параметр компоновщика"
  - "-FIXED - параметр компоновщика"
  - "предпочтительный базовый адрес для загружаемой программы"
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FIXED (фиксированный базовый адрес)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FIXED[:NO]  
```  
  
## Заметки  
 Указывает, что операционная система загружает программы только на предпочитаемом его базового адреса.  Если предпочтительный базовый адрес недоступен, операционная система не загружает файл.  Для получения дополнительной информации см. [\/BASE \(базовый адрес\)](../../build/reference/base-base-address.md).  
  
 \/FIXED:NO параметр по умолчанию для библиотеки DLL, и параметр \/FIXED по умолчанию для любых других типов проектов.  
  
 Если задан параметр \/FIXED, то программа LINK не создает в программе секцию перемещения.  Во время выполнения, если операционная система не может загрузить программу по указанному адресу, он выдает сообщение об ошибке и не загружает программы.  
  
 Для создания секции перемещения в программе следует задать параметр \/FIXED:NO.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите имя и параметр в окне **Дополнительные параметры**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)