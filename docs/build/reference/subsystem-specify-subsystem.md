---
title: /SUBSYSTEM (укажите подсистему)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: 3d808f86a9ea3b34da0dccae18ecc000ca364f0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518395"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (укажите подсистему)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>Аргументы

**BOOT_APPLICATION**<br/>
Приложение, которое выполняется в среде загрузки Windows. Дополнительные сведения о приложениях загрузки см. в разделе [о BCD](/previous-versions/windows/desktop/bcd/about-bcd).

**КОНСОЛЬ**<br/>
Приложения символьного режима Win32. Операционная система предоставляет консоль для консольных приложений. Если `main` или `wmain` определяется для машинного кода, `int main(array<String ^> ^)` определяется для управляемого кода, или полностью построить приложение с помощью `/clr:safe`, КОНСОЛИ используется по умолчанию.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Подсистемы Extensible Firmware Interface. Дополнительные сведения см. Примеры см. на сайте Intel. Минимальная версия версии и по умолчанию — 1.0.

**СОБСТВЕННЫЙ**<br/>
В режиме ядра драйверы для Windows NT. Этот параметр обычно зарезервирован для компонентов системы Windows. Если [/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) указан, по умолчанию используется машинный код.

**POSIX**<br/>
Приложение, выполняемое с подсистемой POSIX в Windows NT.

**WINDOWS**<br/>
Приложение не требует консоли, возможно, поскольку он создает собственное окно для взаимодействия с пользователем. Если `WinMain` или `wWinMain` определяется для машинного кода или `WinMain(HISTANCE *, HINSTANCE *, char *, int)` или `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` определяется для управляемого кода по умолчанию — WINDOWS.

*Основные* и *дополнительный номер*<br/>
(Необязательно) Укажите минимальную требуемую версию подсистемы. Аргументы — десятичные числа в диапазоне от 0 до 65 535. См. в разделе "Примечания" Дополнительные сведения. Существуют без верхней границы для номера версий.

## <a name="remarks"></a>Примечания

**/SUBSYSTEM** параметр указывает среду для исполняемого файла.

Выбор подсистемы влияет на символ точки входа (или функцию точки входа), выберет компоновщик.

Минимум необязательный и по умолчанию *основных* и *незначительные* номера версий для подсистем, следующим образом.

|Подсистема|Минимум|Значение по умолчанию|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|CONSOLE|5.01 (x 86) 5.02 (x 64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|ОКНА|5.01 (x 86) 5.02 (x 64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|Машинный код (и DRIVER: WDM)|1,00 (x 86) 1.10 (x64, ARM)|1,00 (x 86) 1.10 (x64, ARM)|
|Машинный код (без /DRIVER:WDM)|4.00 (x 86) 5.02 (x 64) 6.02 (ARM)|4.00 (x 86) 5.02 (x 64) 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите папку Компоновщик.

1. Выберите **системы** страницу свойств.

1. Изменить `SubSystem` свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)