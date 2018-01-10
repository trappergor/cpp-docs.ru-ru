---
title: "-TSAWARE (Создание приложения, поддерживающего сервер терминалов) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs: C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c6fb783f717f730945f8d34c8fe2a03f5e1f6d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (создание приложения, поддерживающего сервер терминалов)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/TSAWARE устанавливает флаг в поле IMAGE_OPTIONAL_HEADER dllcharacteristics в образе программы необязательный заголовок. Если этот флаг установлен, сервер терминалов не будет вносить определенные изменения в приложение.  
  
 Если приложение не поддерживает сервер терминалов (устаревшее приложение), сервер терминалов выполняет определенные изменения в приложении для последующей правильной работы в многопользовательской среде. Например сервер терминалов создаст виртуальную папку Windows, таким образом, что каждый пользователь получит папка Windows, а не начало системный каталог Windows. Это предоставляет пользователям доступ к собственным файлам INI. Кроме того сервер терминалов вносит ряд изменений в реестр приложения прежних версий. Эти изменения снижают скорость загрузки приложения прежних версий на сервере терминалов.  
  
 Если приложение поддерживает сервер терминалов, он должен использовать файлы INI ни записи **HKEY_CURRENT_USER** реестра во время установки.  
  
 Если используется параметр/TSAWARE, а приложение по-прежнему использует ini-файлы, файлы будут совместно использоваться всех пользователей системы. Если допустима, по-прежнему можно связать приложение с/TSAWARE; в противном случае необходимо использовать: No.  
  
 Параметр/TSAWARE включен по умолчанию для Windows 2000 и более поздних версиях для Windows и консольных приложений. В разделе [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) и [/Version](../../build/reference/version-version-information.md) сведения.  
  
 / TSAWARE не подходит для драйверов, VxD или DLL.  
  
 Если приложение было скомпоновано с/TSAWARE, DUMPBIN [/Headers](../../build/reference/headers.md) будут отображаться сведения об ошибке.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **системы** страницу свойств.  
  
4.  Изменить **сервера терминалов** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Хранение сведений о пользователе](http://msdn.microsoft.com/library/aa383452)   
 [Устаревшие приложения в среде служб терминалов](https://msdn.microsoft.com/en-us/library/aa382957.aspx)