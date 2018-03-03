---
title: "Как: Импорт и экспорт ресурсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a01269928d0e5b52cca6e2301ad681db61289f80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-import-and-export-resources"></a>Практическое руководство. Импорт и экспорт ресурсов
Графические ресурсы (растровые изображения, значки, курсоры, панели инструментов), HTML-файлы и пользовательские ресурсы можно импортировать для использования в Visual C++. Эти же типы ресурсов можно экспортировать из проекта Visual C++ в виде отдельных файлов, которые можно использовать за пределами среды разработки.  
  
> [!NOTE]
>  Такие типы ресурсов, как сочетания клавиш, диалоговые окна и таблицы строк, нельзя импортировать или экспортировать, поскольку они не являются типами отдельных файлов.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>Импорт отдельного ресурса в текущий файл ресурса  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши узел описания ресурсов (* .rc) файла, к которому нужно добавить ресурс.  
  
2.  Нажмите кнопку **импорта** в контекстном меню.  
  
3.  Найдите и выберите файл растрового изображения (.bmp), значка (.ico), курсора (.cur), HTML-файл (.htm) или другой файл, который требуется импортировать.  
  
4.  Нажмите кнопку **ОК** для добавления ресурса к выбранному файлу в **ресурсов** представления.  
  
    > [!NOTE]
    >  Процедура импорта выполняется одинаково независимо от конкретного типа выбранного ресурса. Импортированный ресурс автоматически добавляется в соответствующий узел для этого типа ресурса.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>Экспорт растрового изображения, значка или курсора в отдельный файл (для использования за пределами Visual C++)  
  
1.  В **ресурсов** просмотра щелкните правой кнопкой мыши ресурс, который требуется экспортировать.  
  
2.  Нажмите кнопку **Экспорт** в контекстном меню.  
  
3.  В **Экспорт ресурса** диалоговое окно примите текущее имя файла или введите новое.  
  
4.  Перейдите к папке, в которой вы хотите сохранить файл и нажмите кнопку **Экспорт**.  
  

  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)