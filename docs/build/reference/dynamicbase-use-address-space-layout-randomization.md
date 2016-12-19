---
title: "/DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL)) | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RandomizedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE - параметр компоновщика"
  - "DYNAMICBASE - параметр компоновщика"
  - "-DYNAMICBASE - параметр компоновщика"
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, следует ли создавать исполняемый образ, базовый адрес которого может быть случайным образом изменен во время загрузки с помощью технологии ASLR в [!INCLUDE[windowsver](../Token/windowsver_md.md)].  
  
## Синтаксис  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## Заметки  
 По умолчанию \/DYNAMICBASE включен.  
  
 Этот параметр модифицирует заголовок исполняемого файла для указания, должно ли приложение произвольно изменяться во время загрузки.  
  
 В [!INCLUDE[windowsver](../Token/windowsver_md.md)] поддерживается случайный выбор макета адресного пространства.  
  
### Установка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно проекта **Страницы свойств**.  Для получения дополнительной информации см. [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Дополнительно**.  
  
5.  Измените значение свойства **Произвольное изменение базового адреса**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)