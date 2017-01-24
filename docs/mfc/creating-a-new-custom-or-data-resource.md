---
title: "Creating a New Custom or Data Resource | Microsoft Docs"
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
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom resources [C++]"
  - "data resources [C++]"
  - "resources [Visual Studio], creating"
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Custom or Data Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Чтобы создать новый настраиваемый ресурс или ресурс данных, можно поместить ресурс в отдельный файл с помощью обычного синтаксиса файла описания ресурсов \(RC\), а затем включить этот файл в ресурс. Для этого достаточно щелкнуть проект правой кнопкой мыши в обозревателе решений и выбрать в контекстом меню пункт **Включения ресурсов**.  
  
### Создание настраиваемого ресурса или ресурса данных  
  
1.  [Создайте RC\-файл](../windows/how-to-create-a-resource-script-file.md), который содержит настраиваемый ресурс или ресурс данных.  
  
     Пользовательские данные можно ввести в RC\-файл в виде строк в кавычках, заканчивающихся символом null, или как целочисленные значения в десятичном, шестнадцатеричном или восьмеричном формате.  
  
2.  В **обозревателе решений** щелкните правой кнопкой мыши RC\-файл проекта, а затем выберите в контекстном меню пункт **Включения ресурсов**.  
  
3.  В поле **Директивы времени компиляции** введите оператор **\#include**, задающий имя файла, в котором содержится настраиваемый ресурс. Например:  
  
    ```  
    #include mydata.rc  
    ```  
  
     Проверьте синтаксис и орфографию введенных данных. Содержимое поля **Директивы времени компиляции** будет добавляться в файл описания ресурсов в том виде, в каком оно было введено вами.  
  
4.  Нажмите кнопку **ОК**, чтобы записать внесенные изменения.  
  
 Настраиваемый ресурс также можно создать другим способом — импортировав внешний файл. Дополнительные сведения см. в разделе [Импорт и экспорт ресурсов](../windows/how-to-import-and-export-resources.md).  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Binary Editor](../mfc/binary-editor.md)