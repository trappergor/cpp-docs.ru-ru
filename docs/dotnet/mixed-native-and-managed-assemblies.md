---
title: "Смешанные (собственные и управляемые) сборки | Документы Microsoft"
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
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aeb0a4f21487d9d230c72bfbfc6a06928455dfe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mixed-native-and-managed-assemblies"></a>Смешанные (собственные и управляемые) сборки
Смешанные сборки может содержать неуправляемый машинных инструкций и инструкций MSIL. Это позволяет им вызывать и вызываться компоненты .NET, сохраняя совместимость с компонентами, которые полностью неуправляемыми. С помощью смешанных сборок, разработчики могут создавать приложения, используя сочетание управляемых и неуправляемых функций. Благодаря этому смешанные сборки идеально подходит для переноса существующих приложений Visual C++ на платформу .NET.  
  
 Например, существующее приложение, состоящее только из неуправляемых функций можно перенесено на платформу .NET путем повторной компиляции только одного модуля с **/CLR** переключатель компилятора. Этот модуль может использовать возможности .NET, но остается совместим с остальной частью приложения. Таким образом приложения могут преобразовываться в платформе .NET в виде постепенно, по частям. Даже можно выбрать между управляемым и неуправляемым компиляцию для каждой функции, функции в одном файле (в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md)).  
  
 Visual C++ поддерживает создание трех различных типов управляемых сборок: смешанных, чистых и проверяемых. Последний два рассматриваются в [чистый и проверяемый код (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Как: переход на/CLR](../dotnet/how-to-migrate-to-clr.md)  
 Описание рекомендуемых действий по введению или обновлению функций .NET в приложении.  
  
 [Как: компиляция кода MFC и ATL с помощью параметра/CLR](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 Рассматриваются способы компиляции программ MFC и ATL целевой общеязыковая среда выполнения.  
  
 [Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md)  
 Описывает проблемы «блокировкой загрузчика» и решения.  
  
 [Поддержка библиотек для смешанных сборок](../dotnet/library-support-for-mixed-assemblies.md)  
 Описываются способы использования собственных библиотек в **/CLR** компиляций.  
  
 [Особенности производительности](../dotnet/performance-considerations-for-interop-cpp.md)  
 Описывает влияние на производительность смешанных сборок и маршалинга данных.  
  
 [Домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md)  
 Обсуждение поддержки Visual C++ для доменов приложений.  
  
 [Двойное преобразование](../dotnet/double-thunking-cpp.md)  
 Описывает основную точку входа для управляемой функции влияет на производительность.  
  
 [Способы избегания исключений во CLR завершение работы при использовании COM объектов, построенных с помощью/CLR](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 Описывает, как правильного завершения работы управляемого приложения, использующего COM-объект, скомпилированный с **/CLR**.  
  
 [Практическое руководство. Создание приложения с частичным доверием путем удаления зависимости от библиотеки DLL CRT](../dotnet/create-a-partially-trusted-application.md)  
 В этом разделе рассматривается создание с помощью Visual C++ путем удаления зависимости от библиотеки msvcm90.dll общеязыковая среда выполнения приложения с частичным доверием.  
  
 Дополнительные сведения о рекомендации по программированию для смешанных сборок см. в статье MSDN «Общие сведения о из управляемый или неуправляемый код взаимодействия» в [http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp).  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)