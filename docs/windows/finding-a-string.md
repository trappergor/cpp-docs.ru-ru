---
title: "Поиск строки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a66b5dd34aa21a2a0791ecbc71bfd4abcc90c4fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="finding-a-string"></a>Поиск строки
Для поиска одного или нескольких строк в таблице строк и использовать [регулярных выражений](/visualstudio/ide/using-regular-expressions-in-visual-studio) с **поиск в файлах** команда (**изменить** меню) для поиска всех строк которые соответствуют шаблону.  
  
### <a name="to-find-a-string-in-the-string-table"></a>Чтобы найти строку в таблице строк  
  
1.  Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  На **изменить** меню, нажмите кнопку **поиск и замена**, затем выберите **найти**.  
  
3.  В **найти** выберите предыдущую строку поиска из раскрывающегося списка или введите заголовок текст или идентификатор ресурса строки, которые требуется найти.  
  
4.  Выберите любой из **найти** параметры.  
  
5.  Нажмите кнопку **Найти далее**.  
  
    > [!TIP]
    >  Чтобы выполнить поиск файлов с использованием регулярных выражений, используйте **поиск в файлах** команды. Введите регулярное выражение, соответствующих шаблону, или нажмите кнопку справа от **найти** поле, чтобы отобразить список регулярных выражений. При выборе выражения из этого списка оно подставляется как текст для поиска в **найти** поле. Если вы используете регулярные выражения, нужно убедиться, что **использовать: регулярные выражения** установлен флажок.  
  
 Сведения о добавлении ресурсов в управляемые проекты (предназначенные общеязыковая среда выполнения), см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6);  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор строк](../windows/string-editor.md)   

