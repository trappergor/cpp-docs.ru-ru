---
title: "Creating a Menu | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.menu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mnemonics, associating menu items"
  - "menus, associating commands with mnemonic keys"
  - "menus, creating"
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Окно ресурсов недоступно в выпусках Express.  
  
### Создание стандартного меню  
  
1.  В меню **Вид** выберите пункт **Представление ресурсов**, а затем щелкните правой кнопкой мыши заголовок **Меню** и выберите команду **Добавить ресурс**. Выберите **Меню**.  
  
2.  Выберите в строке меню поле **Новый элемент** \(прямоугольник с надписью "Прототип для текста"\).  
  
     ![Поле "Создать элемент" в редакторе меню](../Image/vcMenuEditorNewItemBox.gif "vcMenuEditorNewItemBox")  
Поле "Новый элемент"  
  
3.  Введите название нового меню, например "Файл".  
  
     Введенный текст отображается в редакторе **меню** и в поле **Заголовок**[окна свойств](../Topic/Properties%20Window.md). Вы можете изменять свойства нового пункта меню в любом из этих мест.  
  
     Как только вы присвоите название новому меню в строке меню, поле нового элемента сдвинется вправо \(чтобы вы могли добавить еще одно меню\), а другое поле нового элемента откроется под первым меню, чтобы вы могли добавить в него команды.  
  
     ![Раскрытое поле "Создать элемент"](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")  
Поле нового элемента со смещенным фокусом после ввода названия меню  
  
    > [!NOTE]
    >  Чтобы создать меню с одним пунктом в строке меню, установите значение свойства "Контекстное меню" равным False.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Menu Editor](../Topic/Menu%20Editor.md)