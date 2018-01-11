---
title: "Справки (Справка HTML) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96cd6ad904439f556f2baa51602353ea00c5ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="help-files-html-help"></a>Файлы справки (справка HTML)
Следующие файлы создаются при добавлении поддержки справки типа HTML-справки в приложение, выбрав **контекстной справки** флажок, а затем выбрав **формат HTML-справки** в [Дополнительные функции](../mfc/reference/advanced-features-mfc-application-wizard.md) мастера приложений MFC.  
  
|Имя файла|Расположение каталога|Расположение в обозревателе решений|Описание:|  
|---------------|------------------------|--------------------------------|-----------------|  
|*ProjName*.hhp|*ProjName*\hlp|файлы справки HTML|Файл справки проекта. Он содержит данные, необходимые для компиляции файлов справки в HXS-файл или CHM-файл.|  
|*ProjName*.hhk|*ProjName*\hlp|файлы справки HTML|Содержит список разделов справки.|  
|*ProjName*.hhc|*ProjName*\hlp|файлы справки HTML|Содержимое проекта справки.|  
|Makehtmlhelp.bat|*ProjName*|Исходные файлы|Используется системой для построения проекта справки при компиляции проекта.|  
|Afxcore.htm|*ProjName*\hlp|Разделы справки HTML|Содержит стандартные разделы справки для обычных команд MFC и объектов экрана. Добавьте собственные разделы справки в этот файл.|  
|Afxprint.htm|*ProjName*\hlp|Разделы справки HTML|Содержит разделы справки для команд печати.|  
|*.jpg; \*.gif|*ProjName*\hlp\Images|Файлы ресурсов|Содержать изображения для различных разделов создаваемых файлов справки.|  
  
## <a name="see-also"></a>См. также  
 [Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)