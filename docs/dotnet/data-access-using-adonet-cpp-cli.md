---
title: "Доступ к данным с помощью ADO.NET (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fb7d184ebdb537c02b79a412d69a4bdcaabde424
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-access-using-adonet-ccli"></a>Доступ к данным с помощью ADO.NET (C++/CLI)
ADO.NET является API .NET Framework для доступа к данным и обеспечивает мощность и простоту использования возможности, недоступные в предыдущих решений доступа к данных. В этом разделе описываются некоторые вопросы, касающиеся ADO.NET, которые являются уникальными для пользователей Visual C++, такие как маршалинг типов.  
  
 ADO.NET выполняется под Common Language Runtime (CLR). Таким образом приложения, взаимодействующие с ADO.NET необходимо также среды CLR. Однако, это означает, что собственного приложения не могут использовать ADO.NET. Эти примеры демонстрируют взаимодействовать с базой данных ADO.NET из машинного кода.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Маршалинг строк ANSI для ADO.NET (C++/CLI)](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг строк BSTR для ADO.NET (C++/CLI)](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг строк Юникода для ADO.NET (C++/CLI)](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг VARIANT для ADO.NET (C++/CLI)](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Практическое руководство. Маршалинг безопасного массива SAFEARRAY для ADO.NET (C++/CLI)](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## <a name="related-sections"></a>Связанные разделы  
  
|Раздел|Описание:|  
|-------------|-----------------|  
|[ADO.NET](/dotnet/framework/data/adonet/index)|Общие сведения о ADO.NET, набор классов, предоставляющих службы доступа к данным программистам .NET.|  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)