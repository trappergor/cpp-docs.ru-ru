---
title: "/FUNCTIONPADMIN (создание образа, допускающего горячее обновление) | Microsoft Docs"
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
  - "/functionpadmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FUNCTIONPADMIN - параметр компоновщика"
  - "-FUNCTIONPADMIN - параметр компоновщика"
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FUNCTIONPADMIN (создание образа, допускающего горячее обновление)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Готовит образ к оперативному исправлению.  
  
## Синтаксис  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## Заметки  
 где  
  
 `space` \(необязательно\)  
 Сумма заполнения, добавляемый в начало каждой функции, 5, 6 или 16. для изображения x86, x64 5 байт заполнения образы требуется 6 байт, и кода, сформированного для Itanium Processor Family требуют заполнения 16 байт в начале каждой функции.  
  
 По умолчанию компилятор заполняет требуемый объем, основываясь на типе машины образа.  
  
 Чтобы компоновщик мог подготовить образ к горячему обновлению, OBJ\-файлы следует компилировать с параметром [\/hotpatch \(Создать образ с обновлениями\)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 Если при вызове программы cl.exe образ компилируется и компонуется одновременно, то наличие параметра **\/hotpatch** подразумевает наличие параметра **\/functionpadmin**.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр в поле **Дополнительные параметры**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)