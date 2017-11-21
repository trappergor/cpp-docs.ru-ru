---
title: "Изменение строки в ресурсе сведений о версии | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.version
dev_langs: C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4547247a2ab9dc5b8ca98aae6838d9891f4ab49f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="editing-a-string-in-a-version-information-resource"></a>Изменение строки в ресурсе сведений о версии
### <a name="to-edit-a-string-in-a-version-information-resource"></a>Изменение строки в ресурсе сведений о версии  
  
1.  Щелкните элемент один раз, чтобы выбрать его, а затем щелкните его повторно, чтобы приступить к редактированию. Изменения следует вносить непосредственно в таблице сведений о версии или в [окне свойств](/visualstudio/ide/reference/properties-window). Внесенные изменения будут отображаться и там, и там.  
  
     **Примечание.** В процессе редактирования раздела **FILEFLAGS** в редакторе сведений о версии вы можете обратить внимание на то, что для RC-файлов нельзя задать значения свойств **Debug**, **Private Build**и **Special Build** в окне свойств.  
  
    -   Редактор сведений о версии задает для свойства **Debug** значение #ifdef в описании ресурса в зависимости от флага сборки **_DEBUG** .  
  
    -   Если для раздела **Private Build** в таблице сведений о версии задано **Значение** , для соответствующего свойства **Private Build** (в окне свойств) раздела **FILEFLAGS** будет задано значение **True**. Если **Значение** пусто, это свойство будет иметь значение **False**. Аналогичным образом раздел **Special Build** (в таблице сведений о версии) связан со свойством **Special Build** раздела **FILEFLAGS** .  
  
 Чтобы отсортировать строки в блоке, щелкните заголовок столбца "Раздел" или "Значение". В результате сведения автоматически будут отображаться в порядке, заданном сортировкой.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор сведений о версии](../windows/version-information-editor.md)   
 [Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

