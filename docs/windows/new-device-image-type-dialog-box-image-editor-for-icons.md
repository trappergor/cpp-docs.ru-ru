---
title: "Диалоговое окно &quot;Создание типа изображения &lt;устройство&gt;&quot; (редактор изображений для значков) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.newimagetype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Диалоговое окно "Создание типа изображения <устройство>""
ms.assetid: 9c1344f5-dea0-42cd-9042-b13032f72be2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Диалоговое окно &quot;Создание типа изображения &lt;устройство&gt;&quot; (редактор изображений для значков)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет создавать новые изображения устройств заданного типа.  Чтобы открыть диалоговое окно **Новое изображение \<название\_устройства\>**, щелкните **Создать тип изображений** в меню **Изображение**.  Дополнительные сведения о размерах значков для Windows см. в разделе [Значки](_win32_Icons_cpp) документации по Windows SDK.  
  
 **Конечный тип изображений**  
 Перечисляет доступные типы изображений.  Выберите тип открываемого изображения:  
  
||||  
|-|-|-|  
|-   16 x 16, 16 цветов|-   48 x 48, 16 цветов|-   96 x 96, 16 цветов|  
|-   16 x 16, 256 цветов|-   48 x 48, 256 цветов|-   96 x 96, 256 цветов|  
|-   16 x 16, монохромный|-   48 x 48, монохромный|-   96 x 96, монохромный|  
|-   32 x 32, 16 цветов|-   64 x 64, 16 цветов||  
|-   32 x 32, 256 цветов|-   64 x 64, 256 цветов||  
|-   32 x 32, монохромный|-   64 x 64, монохромный||  
  
> [!NOTE]
>  Существующие изображения не представлены в этом списке.  
  
 **Пользовательское**  
 Позволяет открыть диалоговое окно [Настраиваемое изображение](../mfc/custom-image-dialog-box-image-editor-for-icons.md), с помощью которого можно создать новое изображение другого размера и с другим набором цветов.  
  
## Требования  
 None  
  
## См. также  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Меню "Изображение"](../mfc/image-menu-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)