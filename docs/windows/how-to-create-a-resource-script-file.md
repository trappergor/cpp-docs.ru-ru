---
title: "How to: Create a Resource Script File | Microsoft Docs"
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
  - "rc files, creating"
  - ".rc files, creating"
  - "resource script files, creating"
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# How to: Create a Resource Script File
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Редактор ресурсов недоступен в выпусках Express.  
>   
>  Этот материал относится к классическим приложениям Windows. В проектах на языках .NET файлы описания ресурсов не используются. Дополнительные сведения см. в разделе [Файлы ресурсов](../mfc/resource-files-visual-studio.md).  
  
### Создание файла описания ресурсов \(RC\)  
  
1.  Выберите в `Solution Explorer` папку существующего проекта, например MyProject.  
  
    > [!NOTE]
    >  Не перепутайте папку проекта с папкой решения в обозревателе решений. Если поместить фокус на папке решения, в диалоговом окне **Добавление нового элемента** \(в шаге 3\) будут отображаться другие варианты.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
3.  В диалоговом окне **Добавление нового элемента** выберите папку **Visual C\+\+**, а затем выберите в правой области **Файл ресурсов \(.rc\)**.  
  
4.  Укажите имя файла описания ресурсов в текстовом поле **Имя** и нажмите кнопку **Открыть**.  
  
 Теперь можно [создать](../windows/how-to-create-a-resource.md) ресурсы и добавить их в RC\-файл.  
  
> [!NOTE]
>  Файл описания ресурсов \(RC\) можно добавить только в существующий проект, загруженный в интегрированную среду разработки Visual Studio. Нельзя создать автономный RC\-файл \(за пределами проекта\).[Шаблоны ресурсов](../Topic/How%20to:%20Use%20Resource%20Templates.md) \(RCT\-файлы\) можно создать в любой момент.  
  
 Требования  
  
 Win32  
  
## См. также  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)