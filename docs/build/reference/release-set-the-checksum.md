---
title: "/RELEASE (установить контрольную сумму) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/release"
  - "VC.Project.VCLinkerTool.SetChecksum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE - параметр компоновщика"
  - "установка контрольной суммы"
  - "RELEASE - параметр компоновщика"
  - "-RELEASE - параметр компоновщика"
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /RELEASE (установить контрольную сумму)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## Заметки  
 Параметр \/RELEASE задает контрольную сумму в заголовке EXE\-файла.  
  
 Операционная система запрашивает контрольную сумму для драйверов устройств.  Чтобы гарантировать совместимость с будущими операционными системами, следует устанавливать контрольную сумму для окончательных версий драйверов устройств.  
  
 Если указан параметр [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md), то параметр \/RELEASE устанавливается по умолчанию.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Перейдите на страницу свойств **Дополнительно**.  
  
4.  Измените значение свойства **Установить контрольную сумму**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)