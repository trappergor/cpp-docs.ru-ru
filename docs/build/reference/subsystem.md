---
title: "/SUBSYSTEM | Microsoft Docs"
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
  - "/subsystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SUBSYSTEM - параметр программы editbin"
  - "SUBSYSTEM - параметр (программа editbin)"
  - "-SUBSYSTEM - параметр (программа editbin)"
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SUBSYSTEM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает среду выполнения, которая необходима для исполняемого образа.  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## Заметки  
 Этот параметр изменяет образ, чтобы указать, какую подсистему необходимо использовать операционной системе для исполнения.  
  
 Можно указать одну из следующих подсистем:  
  
 BOOT\_APPLICATION  
 Приложение, которое выполняется в среде загрузки Windows.  Подробнее о приложениях загрузки см. в разделе [О поставщике BCD WMI](http://msdn.microsoft.com/library/aa362639.aspx).  
  
 CONSOLE  
 Приложения символьного режима Windows.  Операционная система предоставляет консоль для консольных приложений.  
  
 Образ EFI  
 Параметры подсистемы EFI описывают исполняемые образы, которые выполняются в среде Extensible Firmware Interface.  Она обычно предоставляются с оборудованием и запускается перед загрузкой операционной системы.  Основные различия между типами образов EFI — это область памяти, в которую загружается образ, и действие, выполняемое при возвращении вызова к образу.  Образ EFI\_APPLICATION выгружается, когда управление возвращается.  EFI\_BOOT\_SERVICE\_DRIVER и EFI\_RUNTIME\_DRIVER выгружаются, только если управление возвращается с кодом ошибки.  Образ EFI\_ROM выполняется из ПЗУ.  Дополнительные сведения см. в спецификациях на веб\-сайте [Форум Unified EFI](http://www.uefi.org/).  
  
 NATIVE  
 Код, который выполняется без среды подсистемы — например, работающие в режиме ядра драйверы устройств и собственные системные процессы.  Этот параметр обычно зарезервирован для компонентов системы Windows.  
  
 POSIX  
 Приложение, выполняемое в подсистеме POSIX в Windows.  
  
 WINDOWS  
 Приложение, выполняемое в графической среде Windows.  К ним относятся приложения для рабочего стола и приложения Магазина Windows.  
  
 WINDOWSCE  
 Подсистема WINDOWSCE указывает, что приложение предназначено для устройств с ядром Windows CE.  Доступные версии ядра: PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0\-6.0R3 и Windows Embedded Compact 7.  
  
 Необязательные значения `major` и `minor` указывают минимальную требуемую версию заданной подсистемы:  
  
-   Целая часть номера версии \(находится слева от десятичного разделителя\) представлена `major`.  
  
-   Дробная часть номера версии \(находится справа от десятичного разделителя\) представлена `minor`.  
  
-   Значения `major` и `minor` должно иметь значение от 0 до 65 535.  
  
 Выбор подсистемы влияет на начальный адрес программы по умолчанию.  Дополнительные сведения см. в разделе [\/ENTRY \(символ точки входа\)](../../build/reference/entry-entry-point-symbol.md), и описании параметра компоновщика\/ENTRY:*функция*.  
  
 Дополнительные сведения, в том числе о минимальных значениях и значениях по умолчанию для основного и дополнительного номера версии каждой подсистемы, см. в описании параметра компоновщика [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md).  
  
## См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)