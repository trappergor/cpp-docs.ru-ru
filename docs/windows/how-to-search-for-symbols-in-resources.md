---
title: "Как: поиск символов в ресурсах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 154c7a7284272ceef7a3e2d82fcd90d05069b7fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-search-for-symbols-in-resources"></a>Практическое руководство. Поиск символов в ресурсах
### <a name="to-find-symbols-in-resources"></a>Поиск символов в ресурсах  
  
1.  Из **изменить** меню, выберите **поиск символа**.  
  
2.  В [диалоговое окно "Поиск символа"](http://msdn.microsoft.com/en-us/63e93d9c-784f-418d-a76a-723da5ff5d96)в **найти** поле выберите предыдущую строку поиска из раскрывающегося списка или введите сочетание клавиш, которое требуется найти (например, ID_ACCEL1).  
  
    > [!TIP]
    >  Для использования [регулярных выражений](/visualstudio/ide/using-regular-expressions-in-visual-studio) для поиска, необходимо использовать [команда Find in Files](/visualstudio/ide/reference/find-command) из **изменить** меню вместо **поиск символа**команды. Чтобы включить регулярные выражения, необходимо иметь **использование: регулярные выражения** флажком в [диалоговое окно «Поиск»](http://msdn.microsoft.com/en-us/dad03582-4931-4893-83ba-84b37f5b1600). Затем можно щелкнуть кнопку со стрелкой вправо, чтобы в правой части **найти** поле, чтобы отобразить список регулярных выражений. При выборе выражения из этого списка оно подставляется как текст для поиска в **найти** поле.  
  
3.  Выберите любой из **найти** параметры.  
  
4.  Нажмите кнопку **Найти далее**.  
  
    > [!NOTE]
    >  Нельзя выполнять поиск символов в строках, сочетаниях клавиш и двоичных ресурсах.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Символы: Идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)