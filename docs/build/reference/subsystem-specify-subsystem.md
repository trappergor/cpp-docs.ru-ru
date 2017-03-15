---
title: "/SUBSYSTEM (укажите подсистему) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/subsystem"
  - "VC.Project.VCLinkerTool.SubSystem"
  - "VC.Project.VCLinkerTool.SubSystemVersion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SUBSYSTEM - параметр компоновщика"
  - "SUBSYSTEM - параметр компоновщика"
  - "-SUBSYSTEM - параметр компоновщика"
  - "спецификации подсистемы"
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# /SUBSYSTEM (укажите подсистему)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT\_APPLICATION  
 Приложение, которое запускается в среде загрузки Windows.  Дополнительные сведения о приложениях загрузки см. в разделе [О BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639).  
  
 CONSOLE  
 Приложение с символами Win32.  Консольным приложениям операционная система предоставляет консоль.  Если `main` или `wmain`определяется для машинного кода, то `int main(array<String ^> ^)` определяется для управляемого кода, или производится построение приложения полностью за счет использования `/clr:safe`, CONSOLE устанавливается по умолчанию.  
  
 Расширяемый аппаратный интерфейс  
 Подсистемы EFI\_\*.  Дополнительные сведения см. в технической документации по EFI.  Например, см. веб\-узел Intel.  Минимальная версия и версия по умолчанию — 1.0.  
  
 NATIVE  
 Драйверы режима ядра для Windows NT.  Этот параметр обычно резервируется для системных компонентов Windows.  Если [\/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) задан, значение по умолчанию — NATIVE.  
  
 POSIX  
 Приложение, выполняемое с подсистемой POSIX в Windows NT.  
  
 WINDOWS  
 Приложению не требуется консоль, вероятно, потому, что оно создает собственное окно для взаимодействия с пользователем.  Если `WinMain` или `wWinMain`определяется для машинного кода, или `WinMain(HISTANCE *, HINSTANCE *, char *, int)` или `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` определяется для управляемого кода, WINDOWS устанавливается по умолчанию.  
  
 `Major` и `minor`\(необязательно\).  
 Задать минимальное требование к версии подсистемы.  Аргументами являются десятичные числа в диапазоне от 0 до 65535.  Дополнительные сведения см. в разделе "Примечания".  Верхний предел номера версии не ограничен.  
  
## Заметки  
 Параметр \/SUBSYSTEM указывает среду для исполняемого файла.  
  
 Выбор подсистемы влияет на символ точки входа \(или функцию точки входа\), который будет выбран компоновщиком.  
  
 Дополнительно задаваемый минимальный номер версии и значения `major` и `minor` номера версии по умолчанию для подсистемы следующие:  
  
|Подсистема|Минимум|По умолчанию|  
|----------------|-------------|------------------|  
|BOOT\_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 \(x86\) 5.02 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\) 6.02 \(ARM\)|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\(6.00\) \(6.02\) ARM|  
|WINDOWS|5.01 \(x86\) 5.02 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\) 6.02 \(ARM\)|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\(6.00\) \(6.02\) ARM|  
|NATIVE \(с DRIVER:WDM\)|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\), ARM|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\), ARM|  
|NATIVE \(без \/DRIVER:WDM\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\) 6.02 \(ARM\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|POSIX|1.0|19.90|  
|EFI\_APPLICATION, EFI\_BOOT\_SERVICE\_DRIVER, EFI\_ROM, EFI\_RUNTIME\_DRIVER|1.0|1.0|  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку Компоновщик.  
  
3.  Выберите страницу свойств **Система**.  
  
4.  Очистите свойство `SubSystem`.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)