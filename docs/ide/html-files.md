---
title: "HTML-файлы | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "пользовательские мастера, HTML-файлы"
  - "пользовательские мастера, пользовательский интерфейс"
  - "файлы [C++], созданные мастером пользователя"
  - "HTML-страницы, пользовательский интерфейс для мастеров пользователя"
  - "пользовательский интерфейс для мастеров"
  - "мастера [C++], пользовательский интерфейс для мастеров пользователя"
ms.assetid: 3b6ed080-6560-418b-b908-d84d71bdf145
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HTML-файлы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Мастер может содержать пользовательский интерфейс, являющийся интерфейсом HTML.  Помимо файла Default.htm, мастер может содержать любое количество HTM\-файлов, которые можно задать в окне **Число страниц** [Специального мастера](../ide/custom-wizard.md).  Каждый HTM\-файл представляет HTML\-страницу мастера, которая доступна с помощью кнопок `Next` и **Назад**, вкладок или любых других элементов меню, заданных пользователем в мастере создания.  
  
 HTML содержит:  
  
-   Тег "SYMBOL", который указывает умолчания для параметров, заданных пользователем.  Когда пользователь нажимает кнопку **Готово**, символы записываются в таблицу символов. Например:  
  
```  
<SYMBOL NAME='HEADER_FILE' VALUE='MyHeader.h' TYPE=text></SYMBOL>  
```  
  
 В мастере пользовательского интерфейса \(UI\) текстовое поле, идентифицирующееся в таблице символов как "HEADER\_FILE", содержит текст по умолчанию "MyHeader.h".  Данное значение можно изменить в мастере пользовательского интерфейса \(UI\). Новое значение будет записано в таблицу символов проекта при нажатии пользователем кнопки **Готово**. Например:  
  
```  
<SYMBOL NAME='CHECKBOX1' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
 В мастере пользовательского интерфейса \(UI\) флажок, идентифицирующийся в таблице символов как "CHECKBOX1", по умолчанию снят.  Данное поле можно выбрать в мастере пользовательского интерфейса \(UI\) HTML. Новое значение будет записано в таблицу символов проекта при нажатии пользователем кнопки **Готово**.  
  
 Каждый HTM\-файл записывает выбор пользователя в таблицу символов.  
  
-   Файл [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), который содержит часто используемых и полезные функции JScript и Default.js.  
  
-   Ссылки на изображения в проекте, отображаемые в HTML коде.  
  
-   HTML текст и форматирование, которое настраивает представление пользовательского интерфейса мастера.  
  
-   Функции JScript, предоставляющие доступ к моделям объектов мастера Visual C\+\+, чтобы предоставить настраиваемое поведение из мастера.  Данные функции в разделе HTML страницы имеют заголовок \<SCRIPT LANGUAGE\='JSCRIPT'\>, как показано в следующем примере.  
  
    > [!NOTE]
    >  Для доступа к мастеру и моделям объектов среды из HTML, вставьте перед элементом модели объекта "window.external.".  
  
    ```  
    function InitDocument(document)  
    {  
       setDirection();  
  
       if (window.external.FindSymbol('DOCUMENT_FIRST_LOAD'))  
       {  
          // This function sets the default symbols based   
          // on the values specified in the SYMBOL tags above  
          //  
          window.external.SetDefaults(document);  
       }  
  
       // Load the document and initialize the controls   
       // with the appropriate symbol values  
       //  
       window.external.Load(document);  
    }  
    ```  
  
 Ниже приведен пример простого мастера консольного приложения:  
  
```  
<SYMBOL NAME='WIZARD_DIALOG_TITLE' TYPE=text VALUE='Console Application Wizard'></SYMBOL>  
  
<SYMBOL NAME='EMPTY_PROJECT' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_ATL' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_MFC' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)