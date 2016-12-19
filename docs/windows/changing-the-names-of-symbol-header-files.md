---
title: "Changing the Names of Symbol Header Files | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing.header"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource files, multiple"
  - "Resource Includes dialog box"
  - "symbol header files, changing names"
  - "symbol header files"
  - "header files, changing names"
  - "names [C++], symbol header files"
  - "symbols, symbol header files"
  - "Resource.h"
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Names of Symbol Header Files
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обычно все определения символов сохраняются в файле Resource.h.  Однако может возникнуть необходимость изменить имя этого включаемого файла, чтобы, например, работать с несколькими файлами ресурсов, расположенными в одном каталоге.  
  
### Изменение имени файла символов заголовков ресурсов  
  
1.  На панели [Представление ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши RC\-файл и выберите в контекстном меню команду [Включения ресурсов](../windows/resource-includes-dialog-box.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC\-файлов, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В поле **Файл символов заголовков** введите новое имя включаемого файла.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*.  
  
 Требования  
  
 Win32  
  
## См. также  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)