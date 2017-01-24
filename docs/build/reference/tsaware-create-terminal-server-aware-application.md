---
title: "/TSAWARE (создание приложения, поддерживающего сервер терминалов) | Microsoft Docs"
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
  - "/tsaware"
  - "VC.Project.VCLinkerTool.TerminalServerAware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TSAWARE - параметр компоновщика"
  - "Сервер терминалов"
  - "Сервер терминалов, Приложения, поддерживающие сервер терминалов"
  - "TSAWARE - параметр компоновщика"
  - "-TSAWARE - параметр компоновщика"
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TSAWARE (создание приложения, поддерживающего сервер терминалов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TSAWARE[:NO]  
```  
  
## Заметки  
 Параметр \/TSAWARE устанавливает флаг в поле IMAGE\_OPTIONAL\_HEADER DllCharacteristics в необязательном заголовке образа программы.  Когда этот флаг установлен, сервер терминала не вносит определенные изменения в приложения.  
  
 Если приложение не поддерживает сервер терминалов \(приложение прежних версий\), то сервер терминалов выполняет определенные изменения в приложении, чтобы оно выполнялось правильно в многопользовательской среде.  Например, сервер терминалов создает виртуальную папку Windows, чтобы пользователь мог воспользоваться ей, а не системным каталогом Windows.  Пользователь получает доступ к собственным файлам INI.  Кроме этого, сервер терминалов вносит ряд изменений в реестр приложения прежних версий.  Эти изменения снижают скорость загрузки приложения прежних версий на сервере терминалов.  
  
 Если приложение поддерживает сервер терминалов, оно не должно использовать файлы INI или выполнять запись в реестр **HKEY\_CURRENT\_USER** во время установки.  
  
 Если используется параметр \/TSAWARE, а приложение использует файлы INI, эти файлы будут совместно использоваться всеми пользователями системы.  Если такой вариант является допустимым, можно выполнить компоновку приложения с помощью параметра \/TSAWARE. В противном случае необходимо использовать параметр \/TSAWARE:NO.  
  
 Параметр \/TSAWARE по умолчанию включен для Windows 2000 и более поздних версий, а также для приложений Windows и консольных приложений.  Дополнительные сведения см. в описании [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) и [\/VERSION](../Topic/-VERSION%20\(Version%20Information\).md).  
  
 Параметр \/TSAWARE нельзя использовать для драйверов, VxD или DLL.  
  
 Если приложение было скомпоновано с помощью параметра \/TSAWARE, то параметр [\/HEADERS](../../build/reference/headers.md) DUMPBIN будет отображать соответствующую информацию.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Измените свойство **Сервер терминалов**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Storing User\-Specific Information](http://msdn.microsoft.com/library/aa383452)   
 [Legacy Applications in a Terminal Services Environment](https://msdn.microsoft.com/en-us/library/aa382957.aspx)