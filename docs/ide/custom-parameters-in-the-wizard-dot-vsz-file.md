---
title: "Настраиваемые параметры в VSZ-файле мастера | Microsoft Docs"
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
  - "ABSOLUTE_PATH - макрос"
  - "пользовательские мастера, .VSZ-файлы"
  - "HTML_FILTER - макрос"
  - "HTML_PATH - макрос"
  - "IMAGE_FILTER - макрос"
  - "IMAGES_PATH - макрос"
  - "MISC_FILTER - макрос"
  - "PRODUCT - макрос"
  - "PRODUCT_INSTALLATION_DIR - макрос"
  - "PROJECT_TEMPLATE_NAME - макрос"
  - "PROJECT_TEMPLATE_PATH - макрос"
  - "RELATIVE_PATH - макрос"
  - "SCRIPT_COMMON_PATH - макрос"
  - "SCRIPT_FILTER - макрос"
  - "SCRIPT_PATH - макрос"
  - "START_PATH - макрос"
  - "TEMPLATE_FILTER - макрос"
  - "TEMPLATES_PATH - макрос"
  - "WIZARD_NAME - макрос"
  - "WIZARD_UI - макрос"
ms.assetid: 560dd5c0-7cff-4974-b856-5ca25b0669b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Настраиваемые параметры в VSZ-файле мастера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В первых двух строках файла VSZ указывается версия мастера, а также создаваемые идентификаторы ProgID и CLSID мастера.  Файл VSZ также может включать дополнительные параметры контекста и настраиваемые параметры, добавляемые в таблицу символов \(наряду с символами, представленными в разделе символов HTML\).  
  
 Метод <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> служит для отображения мастера, который принимает в качестве параметров массив параметров контекста и настраиваемых параметров, определенных в файле .vsz.  
  
 Следующие распространенные символы указываются в качестве настраиваемых параметров в файле [.vsz file](../ide/dot-vsz-file-project-control.md) или в файле .htm и могут использоваться в файлах шаблонов, скриптов или в HTML\-файлах мастеров.  
  
## Пример  
 Как следует из следующих записей файла .vsz, мастер с именем MyProjWiz содержит пользовательский интерфейс.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine  
Param="WIZARD_NAME = MyProjWiz"  
Param="WIZARD_UI = TRUE"  
```  
  
### Символы настраиваемых параметров в файле .vsz мастера  
  
|Символ|Определение|  
|------------|-----------------|  
|ABSOLUTE\_PATH|Расположение файлов мастера.|  
|HTML\_FILTER|Указывается в файле .vsz.  Типы файлов, размещаемые в папке "Файлы HTML" в **обозревателе решений**.  Обычно задается в виде "htm".|  
|HTML\_PATH|Указывается в файле .vsz.  Расположение [HTML\-файлов](../ide/html-files.md) мастера.  По умолчанию принимается START\_PATH\\HTML\\*LANGUAGE* \(где *LANGUAGE* — это языковой стандарт, указанный в системном реестре\). **Note:**  Можно задать другие языковые настройки, установив для \<LangID\> десятичное значение из ключа HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage.  Дополнительные сведения см. в разделе [Локализация мастера на несколько языков](../ide/localizing-a-wizard-to-multiple-languages.md).  Список десятичных значений и соответствующих им языков см. в разделе [Поддержка мастера для других языков](../ide/wizard-support-for-other-languages.md).|  
|IMAGE\_FILTER|Указывается в файле .vsz.  Типы файлов, размещаемые в папке "Файлы изображений" в обозревателе решений.  Обычно используется "bmp;gif".|  
|IMAGES\_PATH|Указывается в файле .vsz.  Местоположение файлов изображений, используемых в HTML\-файлах.  По умолчанию используется START\_PATH\\Images.|  
|MISC\_FILTER|Указывается в файле .vsz.  Типы файлов, размещаемые в папке "Разное" в обозревателе решений.  Обычно используется "vsz;vsdir;ico;vcproj;csproj;css;inf".|  
|PRODUCT|По умолчанию задается как Visual C\+\+. Однако можно установить значение Visual Basic для создания мастеров Visual Basic и т.д.|  
|PRODUCT\_INSTALLATION\_DIR|Каталог, приведенный в ключе реестра HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\\<Продукт\>\\ ProductDir.|  
|PROJECT\_TEMPLATE\_NAME|Указывается в файле .vsz.  Файлы шаблонов проекта, используемые мастером для создания проектов.  Обычно используется "txt".|  
|PROJECT\_TEMPLATE\_PATH|Каталог, содержащий [файлы шаблонов](../ide/template-files.md) проекта.  Для Visual C\+\+ по умолчанию принимается PRODUCT\_INSTALLATION\_DIR\\VCWizards.|  
|RELATIVE\_PATH|Если путь ABSOLUTE\_PATH не был найден, используется путь RELATIVE\_PATH.  Этот путь определяется относительно каталога PRODUCT\_INSTALLATION\_DIR.  Для Visual C\+\+ RELATIVE\_PATH по умолчанию устанавливается как PRODUCT\_INSTALLATION\_DIR\\VCWizards.|  
|SCRIPT\_COMMON\_PATH|Каталог, заданный относительно PRODUCT\_INSTALLATION\_DIR, в котором находится файл общего скрипта.  Например, для Visual C\+\+ используется VCWizards.|  
|SCRIPT\_FILTER|Указывается в файле .vsz.  Типы файлов, размещаемые в папке "Файлы скриптов" в обозревателе решений.  Обычно задается как "js" \(JScript\) or "vbs" \(VBScript\).|  
|SCRIPT\_PATH|Местоположение [файла JScript](../ide/jscript-file.md) мастера.  По умолчанию используется START\_PATH\\Scripts.|  
|START\_PATH|Указывается в файле .vsz.  Не устанавливается пользователем. Используется для определения RELATIVE\_PATH или ABSOLUTE\_PATH.  Имя мастера \(WIZARD\_NAME\) добавляется к этому значению.|  
|TEMPLATE\_FILTER|Указывается в файле .vsz.  Типы файлов, размещаемые в папке "Файлы шаблонов" в обозревателе решений.  Обычно используется "txt".|  
|TEMPLATES\_PATH|Указывается в файле .vsz.  Местоположение файлов шаблонов мастера.  По умолчанию используется START\_PATH\\Templates\\\<LangID\>. **Note:**  Дополнительные сведения об идентификаторе LangID см. в описании HTML\_PATH.|  
|WIZARD\_NAME|Задает имя мастера.  Указывается в файле .vsz и используется остальными символами.|  
|WIZARD\_UI|Указывается в файле .vsz.  Логическое значение, определяющее, имеет ли мастер пользовательский интерфейс.  В случае наличия пользовательского интерфейса устанавливается значение **TRUE**; в противном случае устанавливается значение **FALSE**.|  
  
## См. также  
 <xref:EnvDTE.IDTWizard.Execute%2A>   
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)