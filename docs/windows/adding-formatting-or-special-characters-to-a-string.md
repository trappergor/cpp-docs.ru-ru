---
title: "Adding Formatting or Special Characters to a String | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "special characters, adding to strings"
  - "ASCII characters, adding to strings"
  - "strings [C++], formatting"
  - "strings [C++], special characters"
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Formatting or Special Characters to a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Добавление форматирования или специальных символов в строки  
  
1.  Откройте таблицу строк, дважды щелкнув соответствующий значок в [представлении ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Выберите строку, которую необходимо изменить.  
  
3.  В [окне свойств](../Topic/Properties%20Window.md) добавьте любую из нижеперечисленных стандартных escape\-последовательностей в текст в поле **Заголовок** и нажмите клавишу **ВВОД**.  
  
    |Желаемый результат|Текст для ввода|  
    |------------------------|---------------------|  
    |Новая строка|\\n|  
    |Возврат каретки|\\r|  
    |Вкладка|\\t|  
    |обратная косая черта \(\\\).|\\\\|  
    |символ ASCII|\\ddd \(восьмеричная система\)|  
    |Предупреждение \(звонок\)|\\a|  
  
> [!NOTE]
>  Редактор строк не поддерживает весь набор управляющих символов ASCI целиком.  Допустимыми являются только символы, представленные в списке.  
  
 Сведения о добавлении ресурсов в управляемые проекты \(предназначенные для выполнения в общеязыковой среде CLR\) см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [String Editor](../mfc/string-editor.md)   
 [Строки](_win32_Strings)   
 [О строках](_win32_About_Strings_cpp)