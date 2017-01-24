---
title: "Функции JScript для мастеров C++ | Microsoft Docs"
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
  - "методы мастера JScript"
  - "методы мастера JScript, создание мастера С++"
ms.assetid: f3046c56-cf67-4aaa-919e-8c066bfb6760
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функции JScript для мастеров C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[AddATLSupportToProject](../ide/addatlsupporttoproject.md)|Добавляет поддержку ATL в проект MFC.|  
|[AddCoclassFromFile](../Topic/AddCoclassFromFile.md)|Воспроизводит и вставляет в IDL\-файл проекта файл шаблона, содержащий компонентный класс.|  
|[AddCommonConfig](../ide/addcommonconfig.md)|Добавляет в проект конфигурации по умолчанию.|  
|[AddFilesToProject](../Topic/AddFilesToProject.md)|Добавляет все файлы в проект, основанный на списке в файле Templates.inf.|  
|[AddInterfaceFromFile](../ide/addinterfacefromfile.md)|Воспроизводит и вставляет в IDL\-файл проекта файл шаблона, содержащий интерфейс.|  
|[Функция CanAddATLClass](../ide/canaddatlclass.md)|Вызывается мастером для проверки совместимости проекта с запускаемым мастером кодов \(иными словами, может ли проект принимать класс ATL\).<br /><br /> Мастер вызывает данную функцию, если параметр PREPROCESS\_FUNCTION находится [в VSZ\-файле элемента управления проекта](../ide/dot-vsz-file-project-control.md) и проверяет доступность [Visual C\+\+ Code Model](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.|  
|[Функция CanAddClass](../ide/canaddclass.md)|Мастер вызывает данную функцию, если параметр PREPROCESS\_FUNCTION находится в VSZ\-файле элемента управления проекта.<br /><br /> Он проверяет, доступен ли объект "Модель кода Visual C\+\+".  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.|  
|[CanAddMFCClass](../ide/canaddmfcclass.md)|Вызывается мастером для проверки совместимости проекта с запускаемым мастером кодов \(иными словами, может ли проект принимать класс MFC\).<br /><br /> Мастер вызывает данную функцию, если в файле элемента управления проекта .vsz имеется параметр PREPROCESS\_FUNCTION, и проверяет доступность объекта модели кода Visual C\+\+.  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.|  
|[CanAddNonAttributed](../ide/canaddnonattributed.md)|Указывает, поддерживает ли проект оба вида объектов ATL — и атрибутированный, и неатрибутированный.|  
|[CanUseFileName](../ide/canusefilename.md)|Определяет, существует ли файл.  Если да, мастер предлагает пользователю объединить код, который должен быть добавлен в существующий файл.|  
|[ConvertProjectToAttributed](../Topic/ConvertProjectToAttributed.md)|Преобразует проект ATL в атрибутированный.|  
|[CreateInfFile](../Topic/CreateInfFile.md)|Создает файл Templates.inf.|  
|[CreateProject](../ide/createproject.md)|Создает проект С\+\+.|  
|[CreateSafeName](../ide/createsafename.md)|Создает понятное имя C\+\+.|  
|[DeleteFile](../ide/deletefile.md)|Удаляет указанный файл.|  
|[DoesIncludeExist](../ide/doesincludeexist.md)|Указывает, существует ли в файле оператор `#include`.|  
|[GetCodeForDllCanUnloadNow](../Topic/GetCodeForDllCanUnloadNow.md)|Извлекает код, нужный для выгрузки библиотеки DLL.|  
|[GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)|Извлекает код для объекта класса DLL.|  
|[GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)|Извлекает код, который должен регистрировать сервер.|  
|[GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)|Извлекает код, который должен отменять регистрацию сервера.|  
|[GetCodeForExitInstance](../Topic/GetCodeForExitInstance.md)|Вспомогательная функция для получения текста для `ExitInstance`.|  
|[GetCodeForInitInstance](../ide/getcodeforinitinstance.md)|Вспомогательная функция для получения текста для [InitInstance](../Topic/CWinApp::InitInstance.md).|  
|[GetExportPragmas](../Topic/GetExportPragmas.md)|Извлекает прагмы для функций экспорта.|  
|[Функция GetInterfaceClasses](../Topic/GetInterfaceClasses.md)|Возвращает объект `VCCodeClass`, связанный с интерфейсом.|  
|[GetInterfaceType](../ide/getinterfacetype.md)|Возвращает тип интерфейса \(например пользовательский, сдвоенный, диспетчерский интерфейс, автоматизированный OLE\).|  
|[GetMaxID](../ide/getmaxid.md)|Возвращает самый верхний `dispid` из элементов этого интерфейса и всех его оснований.|  
|[GetMemberfunction](../Topic/GetMemberfunction.md)|Возвращает объект функции, основанный на данном имени.|  
|[GetProjectFile](../Topic/GetProjectFile.md)|Возвращает имя файла для типа файлов каждого проекта \(RC, IDL и т.д.\).|  
|[GetProjectPath](../ide/getprojectpath.md)|Возвращает путь к каталогу проекта.|  
|[GetRuntimeErrorDesc](../ide/getruntimeerrordesc.md)|Возвращает описание типа исключения.|  
|[GetUniqueFileName](../Topic/GetUniqueFileName.md)|Возвращает уникальное имя файла.|  
|[Функция IncludeCodeElementDeclaration](../ide/includecodeelementdeclaration.md)|Добавляет оператор include в `strInFile`, включая заголовок, где `strCodeElemName` реализуется, если такой заголовок найден в проекте.|  
|[InsertIntoFunction](../ide/insertintofunction.md)|Вспомогательная функция, вызываемая а `AddATLSupportToProject` для включения кода в `InitInstance`.|  
|[Функция IsATLProject](../ide/isatlproject.md)|Указывает, основан ли проект на библиотеке ATL.|  
|[Функция IsAttributedProject](../Topic/IsAttributedProject.md)|Указывает, имеет ли проект атрибуты.|  
|[IsMFCProject](../Topic/IsMFCProject.md)|Проверяет, основан ли проект на MFC.|  
|[LineBeginsWith](../ide/linebeginswith.md)|Вспомогательная функция, вызываемая в `InsertIntoFunction` для определения, начинается ли строка с определенной строки|  
|[OffsetToLineNumber](../ide/offsettolinenumber.md)|Находит номер строки для данной позиции в теле функции.|  
|[OnWizFinish](../Topic/OnWizFinish.md)|Эта функция вызывается из HTML\-скрипта мастера при нажатии пользователем кнопки **Готово**.  Вызывает метод **Готово** элемента управления мастера.|  
|[Функция RenderAddTemplate](../Topic/RenderAddTemplate.md)|Воспроизводит файл шаблона и, при необходимости, добавляет его в проект.|  
|[SetCommonPchSettings](../ide/setcommonpchsettings.md)|Устанавливает предкомпилированный заголовок для проекта.|  
|[Функция SetErrorInfo](../ide/seterrorinfo.md)|Предоставляет сведения об ошибке.|  
|[SetFilters](../ide/setfilters.md)|Добавляет фильтры источников, включения и ресурсов для папок проекта.|  
|[SetMergeProxySymbol](../ide/setmergeproxysymbol.md)|Вызывается мастером для добавления символа \_MERGE\_PROXYSTUB, если это необходимо.|  
|[SetNoPchSettings](../ide/setnopchsettings.md)|Устанавливает свойства конфигурации проекта, если предкомпилированный заголовок не используется.|  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)