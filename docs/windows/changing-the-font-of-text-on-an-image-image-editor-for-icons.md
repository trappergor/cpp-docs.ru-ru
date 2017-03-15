---
title: "Changing the Font of Text on an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "fonts, changing on an image"
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Changing the Font of Text on an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приведенная ниже процедура иллюстрирует следующее:  
  
-   Добавление текста в значок в приложении Windows  
  
-   Управление шрифтом  
  
### Изменение шрифта текста на изображении  
  
1.  Создайте приложение C\+\+ Windows Forms.  Дополнительные сведения см. в разделе [Создание проекта приложения Windows](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  По умолчанию [шаблон приложения Windows Forms](http://msdn.microsoft.com/ru-ru/1babdebf-ab3f-4a64-a608-98499a5b9cea) добавляет в проект файл app.ico.  
  
2.  Дважды щелкните файл app.ico в обозревателе решений.  Откроется [Редактор изображения](../mfc/image-editor-for-icons.md).  
  
3.  В меню **Изображение** выберите пункт **Инструменты**, а затем выберите пункт **Текст**.  Появится диалоговое окно [Текст](../Topic/Text%20Tool%20Dialog%20Box%20\(Image%20Editor%20for%20Icons\).md).  
  
4.  В диалоговом окне "Текст" введите `C++` в любом свободном месте текстовой области.  Текст отобразится в поле с изменяемыми размерами, которое появится в верхнем левом углу значка app.ico в редакторе изображений.  
  
5.  В редакторе изображений перетащите поле с изменяемыми размерами в центр значка app.ico, чтобы текст было лучше видно.  
  
6.  В диалоговом окне "Текст" нажмите кнопку **Шрифт**.  Появится диалоговое окно [Шрифт текста](../mfc/text-tool-font-dialog-box-image-editor-for-icons.md).  
  
7.  В диалоговом окне "Шрифт текста" выберите **Times New Roman** из списка доступных шрифтов в поле со списком **Шрифт**.  
  
8.  Выберите **Полужирный** из списка доступных стилей в поле со списком **Стиль шрифта**.  
  
9. Выберите **10** из списка доступных размеров в поле со списком **Размер**.  
  
10. Нажмите кнопку **ОК**.  Диалоговое окно "Шрифт текста" закроется, и новые параметры шрифта будут применены к тексту.  
  
11. Нажмите кнопку **Закрыть** в диалоговом окне "Текст".  После этого поле с изменяемыми размерами вокруг текста не будет отображаться в редакторе изображений.  
  
## См. также  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Toolbar](../mfc/toolbar-image-editor-for-icons.md)