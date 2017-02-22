---
title: "Файлы справки (справка HTML) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы файлов [C++], файлы справки HTML"
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Файлы справки (справка HTML)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие файлы создаются при добавлении в приложение типа справки HTML поддержки справки, устанавливая флажок **Контекстная справка**, а затем выбирая **формат справки HTML** на странице [Дополнительные возможности](../mfc/reference/advanced-features-mfc-application-wizard.md) мастера приложений MFC.  
  
|Имя файла|Расположение каталога|Расположение в обозревателе решений|Описание|  
|---------------|---------------------------|-----------------------------------------|--------------|  
|*Projname*.hhp|*Projname*\\hlp|Файлы справки HTML|Файл справки проекта.  Он содержит данные, необходимые для компиляции файлов справки в HXS\-файл или в CHM\-файл.|  
|*Projname*.hhp|*Projname*\\hlp|Файлы справки HTML|Содержит индекс разделов справки.|  
|*Projname*.hhp|*Projname*\\hlp|Файлы справки HTML|Содержимое проекта справки.|  
|Makehtmlhelp.bat|*Projname*|Исходные файлы|Используются системой для построения проекта справки, когда компилируется проект.|  
|Afxcore.htm|*Projname*\\hlp|Разделы справки HTML|Содержит стандартные разделы справки для обычных команд MFC и объектов экрана.  Добавьте в этот файл свои собственные разделы.|  
|Afxprint.htm|*Projname*\\hlp|Разделы справки HTML|Содержит разделы справки для команд печати.|  
|\*.jpg; \*.gif|*Projname*\\hlp\\Images|Файлы ресурсов|Содержат изображения для различных разделов создаваемых файлов справки.|  
  
## См. также  
 [Типы файлов, создаваемых для проектов Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)