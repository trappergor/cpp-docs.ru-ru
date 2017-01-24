---
title: "/DELAY (параметры отложенной загрузки импортов) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delay"
  - "VC.Project.VCLinkerTool.DelayNoBind"
  - "VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL"
  - "VC.Project.VCLinkerTool.DelayUnload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY - параметр компоновщика"
  - "DELAY - параметр компоновщика"
  - "-DELAY - параметр компоновщика"
  - "отложенная загрузка библиотек DLL, /DELAY - параметр"
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAY (параметры отложенной загрузки импортов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## Заметки  
 Параметр \/DELAY управляет [отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md) библиотек DLL.  
  
-   Квалификатор UNLOAD предписывает вспомогательной функции отложенной загрузки поддерживать явную выгрузку DLL.  Таблица адресов импорта \(IAT\) восстанавливается в своем первоначальном виде; это приводит к тому, что указатели IAT становятся недействительными и перезаписываются.  
  
     Если квалификатор UNLOAD не указан, то любой вызов [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) завершится с ошибкой.  
  
-   Квалификатор NOBIND предписывает компоновщику не включать связываемую таблицу IAT в окончательный образ.  По умолчанию задано создание связываемой таблицы IAT для библиотек DLL, загружаемых с задержкой.  Полученный в результате образ не может быть статически привязан.  \(Образы с привязываемыми таблицами IAT могут быть статически привязаны перед выполнением.\) См. статью, посвященную параметру [\/BIND](../../build/reference/bind.md).  
  
     Если библиотека DLL привязана, то вспомогательная функция будет пытаться использовать данные привязки вместо вызова функции [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) для каждого из импортов, на которые существует ссылка.  Если отметка времени или предпочтительный адрес не соответствуют таковым в загружаемой библиотеке DLL, то вспомогательная функция будет предполагать, что привязанная таблица IAT устарела, и продолжать обработку так, будто привязанной таблицы IAT не существует.  
  
     Применение квалификатора NOBIND приведет к увеличению образа программы, но зато может уменьшить время загрузки библиотеки DLL.  Если привязка библиотеки DLL не предполагалась, то NOBIND предотвратит создание привязанной таблицы IAT.  
  
 Чтобы задать отложенную загрузку для библиотек DLL, используется параметр [\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md).  
  
### Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Сведения см. в разделе [Работа со свойствами проектов](../../ide/working-with-project-properties.md).\)  
  
2.  Разверните узлы **Свойства конфигурации**, **Компоновщик** и выберите элемент **Дополнительно**.  
  
3.  Измените свойство **Отложенно загружаемые DLL**.  
  
### Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)