---
title: "Конфигурации по умолчанию проекта ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, конфигурация по умолчанию"
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Конфигурации по умолчанию проекта ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В данном разделе сравниваются конфигурации по умолчанию проектов Visual C\+\+ .NET и Visual C\+\+ 6.0.  
  
## Конфигурации по умолчанию в Visual C\+\+ .NET  
 В Visual C\+\+ .NET мастер проектов ATL по умолчанию создает два варианта конфигурации проекта.  
  
### Конфигурации в Visual C\+\+ .NET  
  
|Конфигурация.|Набор символов|Использование ATL|  
|-------------------|--------------------|-----------------------|  
|Release|MBCS|DLL|  
|Отладочная информация|MBCS|DLL|  
  
 Параметры **Набор символов** и **Использование ATL** можно изменить во вкладке **Общие** диалогового окна **Параметры проекта**.  Можно также добавить собственные конфигурации, воспользовавшись диалоговым окном "Диспетчер конфигураций".  Дополнительные сведения см. в разделе [Построение конфигураций](../Topic/Understanding%20Build%20Configurations.md).  
  
## Конфигурации по умолчанию в версии 6.0  
 В Visual C\+\+ версии 6.0 мастер приложений COM ATL \(ATL COM AppWizard\) \(теперь называемый мастером проектов ATL\) по умолчанию создавал шесть конфигураций для проекта.  Эти конфигурации отличались параметрами Release, Debug, Unicode, и использованием параметров CRT и ATL.  При желании все эти конфигурации можно воссоздать в Visual C\+\+ .NET, воспользовавшись диалоговым окном "Диспетчер конфигураций".  
  
### Конфигурации в версии 6.0  
  
|Конфигурация.|Набор символов|Использование ATL|  
|-------------------|--------------------|-----------------------|  
|Отладочная информация|MBCS|Статический|  
|Debug Unicode|UNICODE|Статический|  
|Release Min Dependency|MBCS|Статический|  
|Release Min Dependency Unicode|UNICODE|Статический|  
|Release Min Size|MBCS|DLL|  
|Release Min Size Unicode|UNICODE|DLL|  
  
## См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Работа со свойствами проектов](../../ide/working-with-project-properties.md)   
 [Configuration Manager Dialog Box](http://msdn.microsoft.com/ru-ru/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Построение приложений в Visual Studio](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)