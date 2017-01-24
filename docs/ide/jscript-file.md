---
title: "Файл JScript | Microsoft Docs"
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
  - "AddConfig - метод"
  - "AddFilesToCustomProj - метод"
  - "AddFilters - метод"
  - "Common.js - файл"
  - "CreateCustomInfFile - метод"
  - "CreateCustomProject - метод"
  - "пользовательские мастера, доступ к объектной модели мастера"
  - "пользовательские мастера, файл JScript"
  - "отладка [JScript], включение отладки скрипта"
  - "отладка [JScript], файлы JScript"
  - "отладка скриптов"
  - "отладка скриптов, включение отладки скрипта"
  - "Файл Default.js"
  - "DelFile - метод"
  - "файлы [C++], созданные мастером пользователя"
  - "GetTargetName - метод"
  - "файлы JScript"
  - "OnFinish - метод"
  - "PchSettings - метод"
ms.assetid: 7841a09e-2dd2-4f1a-a13a-39ac53f24315
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Файл JScript
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Специальный мастер](../ide/custom-wizard.md) вызывает обработчик скриптов и создает для каждого проекта файл JScript с именем Default.js.  Он также включает файл [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).  Эти файлы содержат функции JScript, предоставляющие доступ к объектным моделям Visual Studio и Visual C\+\+ для настройки мастера.  \(список моделей см. в разделе [Разработка мастера](../ide/designing-a-wizard.md)\). В файл проекта мастера Default.js можно добавлять и свои собственные функции.  Чтобы получить доступ к свойствам и методам объектной модели мастера или модели среды из файла JScript, следует добавить элемент объектной модели с префиксом "wizard." или "dte." соответственно.  
  
 Примеры.  
  
```  
function CreateCustomProject(strProjectName, strProjectPath)  
{  
   try  
   {  
      var strProjTemplatePath = wizard.FindSymbol('PROJECT_TEMPLATE_PATH');  
var strProjTemplate = '';  
      strProjTemplate = strProjTemplatePath + '\\default.vcproj';  
  
      var Solution = dte.Solution;  
      var strSolutionName = "";  
      if (wizard.FindSymbol("CLOSE_SOLUTION"))  
...  
```  
  
 При нажатии кнопки **Готово** в [специальном мастере](../ide/custom-wizard.md) мастер загружает файл Default.js из папки "Файлы скриптов" обозревателя решений.  Файл JScript создает проекты и предоставляет шаблоны, а затем, когда пользователь нажмет в мастере кнопку **Готово**, добавляет их в решение.  
  
 По умолчанию файл проекта Default.js включает следующие функции:  
  
|Имя функции|Описание|  
|-----------------|--------------|  
|**AddConfig**|Добавляет конфигурации проекта.  Пользователь может задать параметры для компилятора и компоновщика.|  
|**AddFilesToCustomProj**|Добавляет в проект указанные файлы, когда пользователь нажимает кнопку **Готово**.|  
|**AddFilters**|Добавляет в проект указанные фильтры источников, когда пользователь нажимает кнопку **Готово**.|  
|**CreateCustomProject**|Создает проект в указанном расположении, когда пользователь нажимает кнопку **Готово**.|  
|**CreateCustomInfFile**|Создает [файл Templates.inf](../Topic/Templates.inf%20File.md) проекта.|  
|**DelFile**|Удаляет указанный файл.|  
|**GetTargetName**|Возвращает имя указанного файла.|  
|**OnFinish**|Вызывается мастером при нажатии пользователем кнопки **Готово** для создания проекта, добавления файлов и фильтров и задания конфигурации.|  
|**PchSettings**|Задает параметры предварительно скомпилированного заголовка.  Дополнительные сведения см. в описании функции [SetCommonPchSettings](../ide/setcommonpchsettings.md) в справке по Common.js.|  
  
 У каждого мастера имеется уникальный файл Default.js, включающий комментарии TODO, которые помогают определить, где необходимо настраивать этот файл.  
  
 В Visual C\+\+ также имеется файл [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), совместно используемый всеми мастерами и включаемый в новые проекты мастера.  Можно использовать функции в файле Common.js.  
  
> [!NOTE]
>  В файле Common.js содержится описание и параметры для каждой функции.  Дополнительные сведения см. в комментариях в файле Common.js.  
  
 Если имеются функции, которые должны совместно использовать несколько проектов мастеров, можно добавить их в файл Common.js.  Создайте собственную версию Common.js и сохраните ее по общему адресу, а затем задайте путь к этой версии файла в параметре SCRIPT\_COMMON\_PATH [VSZ\-файла](../ide/dot-vsz-file-project-control.md).  
  
> [!NOTE]
>  Мастера, предоставляемые вместе с Visual C\+\+, используют функции JScript из файла Common.js.  При изменении этих функций мастера Visual C\+\+ wizards могут повести себя не так, как ожидается.  
  
 Дополнительные сведения о JScript см. в разделе [Writing, Compiling, and Debugging JScript Code](http://msdn.microsoft.com/ru-ru/13e57e7d-4867-4555-b9e4-fc24aa75e628).  
  
## Отладка скриптов  
 Для отладки скрипта в HTML\-файлах мастера необходимо включить отладку скриптов.  
  
#### Включение отладки скриптов  
  
1.  В обозревателе Internet Explorer в меню **Сервис** выберите пункт **Свойства обозревателя**.  
  
2.  Выберите вкладку **Дополнительно**.  
  
3.  В категории **Обзор** снимите флажок **Запретить отладку скриптов**.  
  
 Это действие также позволит отображать файлы Сommon.js и Default.js в окне **Выполняемые документы** при нажатии в мастере кнопки "Готово".  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)