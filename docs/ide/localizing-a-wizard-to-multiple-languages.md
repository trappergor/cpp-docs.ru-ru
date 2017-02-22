---
title: "Локализация мастера на несколько языков | Microsoft Docs"
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
  - "пользовательские мастера, локализация"
  - "глобализация [C++], мастера"
  - "локализация [C++], мастера"
  - "мастера [C++], локализация"
ms.assetid: 879885c2-fafd-44fd-8032-bf0c301f4f45
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Локализация мастера на несколько языков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Мастер можно создавать на любом языке, поддержку которого предоставляет Visual Studio.  По умолчанию при установке Visual Studio программа установки определяет язык и региональные параметры из реестра и устанавливает соответствующие языковые шаблоны.  
  
 Для идентификации языковой поддержки, необходимой мастеру, Visual Studio использует идентификатор языка.  По умолчанию для идентификатора языка устанавливается десятичное значение записи реестра "HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage".  Если мастер не сможет найти запись языка, то по умолчанию будет установлен английский язык \(English \(1033\)\).  
  
> [!NOTE]
>  Список десятичных значений и соответствующих им языков см. в разделе [Поддержка мастера для других языков](../ide/wizard-support-for-other-languages.md).  
  
 Идентификатор языка задается как настраиваемый параметр в [vsz\-файле](../Topic/Configuring%20.Vsz%20Files%20to%20Start%20Wizards.md) по тем путям, по которым размещены [HTML\-файлы](../ide/html-files.md) и [файлы шаблонов](../ide/template-files.md).  
  
 Необходимо указывать пути для каждого языка, для которого предоставляется HTM\-файл.  
  
## Пример  
 Установка следующих настраиваемых параметров в VSZ\-файле указывает, что HTML\-файл предоставляется на английском \(1033\), японском \(1041\) и немецком \(1031\) языках:  
  
```  
Param="START_PATH\HTML\1033"  
Param="START_PATH\HTML\1041"  
Param="START_PATH\HTML\1031"  
Param="START_PATH\Templates\1033"  
Param="START_PATH\Templates\1041"  
Param="START_PATH\Templates\1031"  
```  
  
 Установка настраиваемых параметров, приведенных выше, задает структуру каталогов мастера следующим образом:  
  
```  
MyWizard1  
   HTML  
      1033  
         default.htm  
         myEnglishHTML.htm  
      1041  
         default.htm  
         myJapaneseHTML.htm  
      1031  
         default.htm  
         myGermanHTML.htm  
   Templates  
      1033  
         stdafx.h  
         stdafx.cpp  
      1041  
         stdafx.h  
         stdafx.cpp  
      1031  
         stdafx.h  
         stdafx.cpp  
   Images  
      HtmlPage1.bmp  
      HtmlPage2.jpg  
   Scripts  
      Default.js  
```  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [Настраиваемые параметры в VSZ\-файле мастера](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)