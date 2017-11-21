---
title: "Создание новых панелей инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.toolbar
dev_langs: C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 84a4e2f81c80551059b11dfa4bd2f78fa71f266f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-new-toolbars"></a>Создание новых панелей инструментов
### <a name="to-create-a-new-toolbar"></a>Чтобы создать новую панель инструментов  
  
1.  В **ресурсов** просмотра, щелкните правой кнопкой мыши RC-файл, а затем выберите **добавить ресурс** из контекстного меню. (При наличии существующую панель инструментов в RC-файле, можно просто щелкнуть **инструментов** папку и выберите **вставить панель инструментов** в контекстном меню.)  
  
     **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В **добавить ресурс** выберите **инструментов** в **тип ресурса** , а затем нажмите кнопку **New**.  
  
     Если появляется знак плюс (+) рядом с **инструментов** тип ресурса, это означает, что доступны шаблоны. Щелкните знак «плюс», чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **New**.  
  
     \- или -  
  
3.  [Преобразование существующего точечного рисунка на панель инструментов](../windows/converting-bitmaps-to-toolbars.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Требования  
  
 MFC или ATL  
  
## <a name="see-also"></a>См. также  
 [Редактор панелей инструментов](../windows/toolbar-editor.md)

