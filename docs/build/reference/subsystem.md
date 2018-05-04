---
title: -SUBSYSTEM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c12df1a2166c9ef5a1af8a33a5764a8899909edb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="subsystem"></a>/SUBSYSTEM
Указывает среду выполнения, которая необходима для исполняемого образа.  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр изменяет образ, чтобы указать, какую подсистему необходимо использовать операционной системе для исполнения.  
  
 Можно указать одну из следующих подсистем:  
  
 BOOT_APPLICATION  
 Приложение, которое выполняется в среде загрузки Windows. Дополнительные сведения о приложениях загрузки см. в разделе [о поставщике BCD WMI](http://msdn.microsoft.com/library/aa362639.aspx).  
  
 CONSOLE  
 Приложения символьного режима Windows. Операционная система предоставляет консоль для консольных приложений.  
  
 Образ EFI  
 Параметры подсистемы EFI описывают исполняемые образы, которые выполняются в среде Extensible Firmware Interface. Она обычно предоставляются с оборудованием и запускается перед загрузкой операционной системы. Основные различия между типами образов EFI — это область памяти, в которую загружается образ, и действие, выполняемое при возвращении вызова к образу. Образ EFI_APPLICATION выгружается, когда управление возвращается. EFI_BOOT_SERVICE_DRIVER и EFI_RUNTIME_DRIVER выгружаются, только если управление возвращается с кодом ошибки. Образ EFI_ROM выполняется из ПЗУ. Дополнительные сведения см. в спецификациях на [форум Unified EFI](http://www.uefi.org/) веб-сайта.  
  
 NATIVE  
 Код, который выполняется без среды подсистемы — например, работающие в режиме ядра драйверы устройств и собственные системные процессы. Этот параметр обычно зарезервирован для компонентов системы Windows.  
  
 POSIX  
 Приложение, выполняемое в подсистеме POSIX в Windows.  
  
 WINDOWS  
 Приложение, выполняемое в графической среде Windows. Сюда входят приложения для настольных компьютеров и приложений универсальной платформы Windows (UWP).  
  
 WINDOWSCE  
 Подсистема WINDOWSCE указывает, что приложение предназначено для устройств с ядром Windows CE. Доступные версии ядра: PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 и Windows Embedded Compact 7.  
  
 Необязательные значения `major` и `minor` указывают минимальную требуемую версию заданной подсистемы:  
  
-   Целая часть номера версии (находится слева от десятичного разделителя) представлена `major`.  
  
-   Дробная часть номера версии (находится справа от десятичного разделителя) представлена `minor`.  
  
-   Значения `major` и `minor` должно иметь значение от 0 до 65 535.  
  
 Выбор подсистемы влияет на начальный адрес программы по умолчанию. Дополнительные сведения см. в разделе [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md), компоновщика/ENTRY:*функция* параметр.  
  
 Дополнительные сведения, включая минимальное и значения по умолчанию для основной и дополнительный номера версии для каждой подсистемы. в разделе [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) компоновщика.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)