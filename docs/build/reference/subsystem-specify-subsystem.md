---
title: "-SUBSYSTEM (Укажите подсистему) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fd96a89ef4228835307f8f8f0d9fff5d61441f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (укажите подсистему)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Приложение, которое выполняется в среде загрузки Windows. Дополнительные сведения о приложениях загрузки см. в разделе [о BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639).  
  
 CONSOLE  
 Символьное приложение Win32. Операционная система предоставляет консоль для консольных приложений. Если `main` или `wmain` определяется для машинного кода, `int main(array<String ^> ^)` определяется для управляемого кода, или полностью построить приложение с помощью `/clr:safe`, CONSOLE устанавливается по умолчанию.  
  
 Extensible Firmware Interface  
 Подсистемы EFI_ *. Дополнительные сведения см. Например, Intel на веб-узле. Минимальная версия версии и по умолчанию — 1,0.  
  
 NATIVE  
 В режиме ядра драйверы для Windows NT. Этот параметр обычно зарезервирован для компонентов системы Windows. Если [/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) указано, по умолчанию используется машинный код.  
  
 POSIX  
 Приложение, выполняемое с подсистемой POSIX в Windows NT.  
  
 ОКНА  
 Приложения не требуется консоль, вероятно, так как она создает собственное окно для взаимодействия с пользователем. Если `WinMain` или `wWinMain` определяется для машинного кода или `WinMain(HISTANCE *, HINSTANCE *, char *, int)` или `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` определяется для управляемого кода по умолчанию — WINDOWS.  
  
 `Major`и `minor` (необязательно)  
 Укажите минимальную требуемую версию подсистемы. Аргументами являются десятичные числа в диапазоне от 0 до 65 535. Дополнительные сведения см. Нет без верхней границы для номера версий.  
  
## <a name="remarks"></a>Примечания  
 Параметр/SUBSYSTEM указывает среду для исполняемого файла.  
  
 Выбор подсистемы влияет на символ точки входа (или функцию точки входа), будет выбран компоновщиком.  
  
 Минимум необязательный и по умолчанию `major` и `minor` номера версий для подсистем, следующим образом.  
  
|Подсистема|Минимум|По умолчанию|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 (x 86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|ОКНА|5.01 (x 86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|Машинный код (DRIVER: WDM)|1,00 (x 86) 1,10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|1,00 (x 86) 1,10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|  
|Машинный код (без /DRIVER:WDM)|4.00 (x 86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|4.00 (x 86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|POSIX|1.0|19.90|  
|EFI_APPLICATION EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку для компоновщика.  
  
3.  Выберите **системы** страницу свойств.  
  
4.  Изменить `SubSystem` свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)