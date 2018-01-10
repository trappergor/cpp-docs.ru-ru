---
title: "-STUB (имя файла заглушки MS-DOS) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs: C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2bb7d1b9f56e7cea5d476d5ece6bdfab50fbe7a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (имя файла-заглушки MS-DOS)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Приложение MS-DOS.  
  
## <a name="remarks"></a>Примечания  
 Параметр/STUB прилагает программу-заглушку MS-DOS к программе Win32.  
  
 Программа-заглушка вызывается в том случае, если файл выполняется в системе MS-DOS. Как правило, выводится соответствующее сообщение; Однако любое допустимое приложение MS-DOS можно программы-заглушки.  
  
 Укажите *filename* для программы-заглушки после двоеточия (:) в командной строке. Компоновщик проверяет *filename* и выдает сообщение об ошибке, если файл не является исполняемым файлом. Программа должна быть файл .exe; .com файл является недопустимым для программы-заглушки.  
  
 Если этот параметр не используется, компоновщик присоединяет программу-заглушку по умолчанию, выдает следующее сообщение:  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 При построении драйвер виртуального устройства, *filename* дает пользователю возможность указать имя файла, который содержит структуру IMAGE_DOS_HEADER (определенную в файле WINNT. (H) для использования в VXD вместо заголовка по умолчанию.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)