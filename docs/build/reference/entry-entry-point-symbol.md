---
title: -ENTRY (символ точки входа) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74d7e6e05af98bb3d3175d352fb3d5de1b70b12b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375403"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (символ точки входа)
```  
/ENTRY:function  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *function*  
 Функция, которая определяет пользовательские начальный адрес для файла с расширением .exe или DLL.  
  
## <a name="remarks"></a>Примечания  
 Параметр/Entry задает функцию точки входа как начальный адрес для файла с расширением .exe или DLL.  
  
 Функция должна быть определена для использования `__stdcall` соглашение о вызовах. Параметры и возвращаемые значения зависят от ли программа консольное приложение, приложение windows или библиотеки DLL. Рекомендуется позволить компоновщику установить точку входа, чтобы правильно инициализирована библиотеки времени выполнения C и C++ конструкторы для статических объектов выполняются.  
  
 По умолчанию начальным адресом является имя функции из библиотеки времени выполнения C. Компоновщик выбирает ее в соответствии с атрибутами программы, как показано в следующей таблице.  
  
|Имя функции|По умолчанию для|  
|-------------------|-----------------|  
|**mainCRTStartup** (или **wmainCRTStartup**)|Приложение, использующее /SUBSYSTEM:CONSOLE; вызовы `main` (или `wmain`)|  
|**Случае** (или **wWinMainCRTStartup**)|Приложения, использующего параметр/SUBSYSTEM:**WINDOWS**; вызовы `WinMain` (или `wWinMain`), который должен быть определен для использования `__stdcall`|  
|**_DllMainCRTStartup**|DLL. вызовы `DllMain` , если он существует, который должен быть определен для использования `__stdcall`|  
  
 Если [/DLL](../../build/reference/dll-build-a-dll.md) или [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметр не указан, то компоновщик выбирает подсистему и точку входа в зависимости от того, следует ли `main` или `WinMain` определен.  
  
 Функции `main`, `WinMain`, и `DllMain` — три формы точки входа, определяемой пользователем.  
  
 При создании управляемого образа, функции, указанной для/Entry должны иметь подпись (LPVOID *переменная1*, DWORD *var2*, LPVOID *var3*).  
  
 Сведения о том, как определять свои собственные `DllMain` точку входа, в разделе [библиотек DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) .  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **точки входа** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)