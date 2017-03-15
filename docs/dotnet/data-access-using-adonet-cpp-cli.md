---
title: "Доступ к данным с помощью ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], доступ к данным"
  - "ADO.NET [C++]"
  - "данные [C++], ADO.NET"
  - "доступ к данным [C++], ADO.NET"
  - "базы данных [C++], получение доступа (C++)"
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Доступ к данным с помощью ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ADO.NET — это интерфейс API платформы .NET Framework, используемый для доступа к данным, предоставляющий мощные и простые в использовании возможности, недоступные в предыдущих версиях решений, предоставляющих доступ к данным.  В этом разделе описываются некоторые вопросы, касающиеся ADO.NET, уникальные для пользователей Visual C\+\+, такие как маршалинг типов.  
  
 ADO.NET выполняется в среде CLR.  Поэтому приложения, взаимодействующие с ADO.NET, также должны компилироваться для среды CLR.  Однако это не означает, что неуправляемые приложения не могут использовать ADO.NET.  В этих примерах показано, как взаимодействовать с базой данных ADO.NET в машинном коде.  
  
## В этом подразделе  
 [Практическое руководство. Маршалинг строк ANSI для ADO.NET](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг строк BSTR для ADO.NET](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалирование строк Юникода для ADO.NET](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг VARIANT для ADO.NET](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг безопасного массива SAFEARRAY для ADO.NET](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## Связанные подразделы  
  
|Раздел|Описание|  
|------------|--------------|  
|[ADO.NET](../Topic/ADO.NET.md)|В этом разделе представлены общие сведения о ADO.NET, наборе классов, предоставляющих службы доступа к данным программистам .NET.|  
|[Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ru-ru/5358a825-e19b-49aa-8214-674ce5fed1da)|Описание способов использования языков платформы .NET Framework, включая Visual C\+\+, для создания объектов баз данных, таких как хранимые процедуры, агрегаты, триггеры, определяемые пользователем функции и типы, а также для извлечения и обновления данных в базах данных Microsoft SQL Server 2005.|  
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)