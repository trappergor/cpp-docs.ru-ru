---
title: "Настройка мастера | Microsoft Docs"
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
  - "пользовательские мастера"
  - "пользовательские мастера, создание в проектах Visual C++"
ms.assetid: a3ff1c81-3eef-41e7-a6bc-2f98e4bf423f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Настройка мастера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При настройке мастера, созданного с помощью программы [Специальный мастер](../Topic/Application%20Settings,%20Custom%20Wizard.md) можно выполнить описанные ниже общие задачи.  
  
-   В VSZ\-файле укажите настраиваемые параметры, необходимые для работы мастера.  Дополнительные сведения см. в разделах [VSZ\-файл \(элемент управления проекта\)](../ide/dot-vsz-file-project-control.md) и [Предопределенные символы специального мастера](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
     Если выполняется локализация мастера на несколько разных языков, добавьте параметры этих языков в VSZ\-файл.  Дополнительные сведения см. в разделе [Локализация мастера на несколько языков](../ide/localizing-a-wizard-to-multiple-languages.md).  
  
-   Чтобы указать директивы для выбора, выполняемого пользователем, настройте [файлы шаблонов](../ide/template-files.md) \(и файл [Templates.inf](../Topic/Templates.inf%20File.md)\).  
  
-   Чтобы указать дополнительную специальную обработку для мастера, настройте [файл Default.js](../ide/jscript-file.md).  Вы можете использовать собственные функции и функции, предоставленные в файле [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).  
  
-   Сконструируйте значки и другие изображения, которые будут использоваться в пользовательском HTML\-интерфейсе.  
  
-   Сконструируйте пользовательский HTML\-интерфейс.  
  
-   Добавьте в таблицу символов HTML символы, соответствующие кнопкам, элементам управления, текстовым полям и другим элементам, используемым в мастере.  
  
     Фрагмент HTML\-кода, предоставленного специальным мастером:  
  
    ```  
    <SYMBOL NAME="WIZARD_DIALOG_TITLE" TYPE=text VALUE="MyCustomWiz">  
          </SYMBOL>  
    <SYMBOL NAME="SAMPLE_CHECKBOX" TYPE=checkbox VALUE=true>  
          </SYMBOL>  
    ```  
  
     Этот мастер под названием MyCustomWiz отображает флажок, который установлен по умолчанию.  
  
-   Чтобы настроить работу мастера, в раздел HTML\-файлов, помеченный символом `<SCRIPT LANGUAGE="JSCRIPT">`, добавьте вызовы функций JScript и доступ к моделям объектов Visual Studio и Visual C\+\+.  Для вызова этих функций необходимо использовать `window.external`, например:  
  
    ```  
    window.external.AddSymbol("MAIN_FRAME_DEFAULT_STYLES", true);  
    window.external.AddSymbol("MAIN_FRAME_STYLE_FLAGS", "");  
    ```  
  
    > [!NOTE]
    >  Методы, свойства и события, предоставленные через [Автоматизация и расширение среды для Visual Studio](../Topic/Automation%20and%20Extensibility%20for%20Visual%20Studio.md), [модель кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b), [модель проекта](http://msdn.microsoft.com/ru-ru/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f) и [модель мастера](http://msdn.microsoft.com/ru-ru/159395ac-33c7-47bf-ad42-4e1435ddc758), позволяют программным образом управлять всеми аспектами проекта мастера, от создания до построения, в файлах JScript и HTM\-файлах.  
  
-   При необходимости настройте [VSDIR\-файл](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md), сделав информацию о VSZ\-файле и всех других шаблонах понятной оболочке.  Например, укажите для значка идентификатор ресурса, флаги, локализованные имена и т. д.  
  
-   Создайте HTM\-файлы и файлы шаблонов во всех языках, для которых требуется локализовать мастер.  Добавьте их в соответствующие каталоги проекта.  
  
-   [Предоставьте контекстную справку](../ide/providing-context-sensitive-help.md) для мастера.  
  
## См. также  
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Этапы проектирования мастера](../ide/steps-to-designing-a-wizard.md)   
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Предоставление контекстной справки.](../ide/providing-context-sensitive-help.md)   
 [Обработка ошибок в мастерах](../ide/handling-errors-in-wizards.md)