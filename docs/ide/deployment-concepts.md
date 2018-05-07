---
title: Основные понятия развертывания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4fa40373e268c76caca17f3466573bc3e830757
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="deployment-concepts"></a>Концепции развертывания
В этом разделе обсуждаются основные моменты при развертывании приложений C++.  
  
## <a name="windows-installer-deployment-in-c"></a>Развертывание установщика Windows в C++  
 Проекты Visual C++ обычно используют традиционный установщик Windows для развертывания. Для подготовки развертывания установщика Windows, пакет приложения в файл setup.exe и распространение этого файла, а также пакет установщика (MSI-файл). Пользователям необходимо будет выполнить setup.exe для установки приложения.  
  
 Пакет приложения путем добавления проекта установки в решение. При построении, он создает установочного пакета файлы, распространять среди пользователей. Дополнительные сведения см. в разделе [Выбор метода развертывания](../ide/choosing-a-deployment-method.md).  
  
## <a name="library-dependencies"></a>Зависимости библиотеки  
 При построении приложения C/C++ с помощью функций, предоставляемых библиотек Visual C++, будет зависеть от наличия этих библиотек во время выполнения. Чтобы выполнение приложения его необходимо связать, статически или динамически необходимые библиотеки Visual C++. Если приложение динамически ссылки библиотеки Visual C++, то при запуске этой библиотеки должен присутствовать, могут быть загружены. С другой стороны Если приложение статически связывается с библиотекой Visual C++, то он не должен соответствующие библиотеки DLL, которые могут присутствовать на компьютере пользователя. Тем не менее, статическая компоновка имеет некоторые отрицательные эффекты, такие как увеличение размера файлов приложения и усложнит обслуживания потенциально. Дополнительные сведения см. в разделе [преимущества использования DLLs](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).  
  
## <a name="packaging-and-redistributing"></a>Упаковка и распространение  
 Библиотеки Visual C++ упаковываются как библиотеки DLL и в Visual Studio на компьютере разработчика установлены все необходимые библиотеки для приложений C/C++. Тем не менее при развертывании приложения для пользователей, он не представляется возможной в большинстве случаев требуется их для установки Visual Studio для запуска приложения. Важно иметь возможность распространять только те части Visual C++, которые необходимы для правильной работы приложения.  
  
 Дополнительные сведения об упаковке и распространении см. в следующих разделах:  
  
-   [Определение библиотек DLL для распространения](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Выбор метода развертывания](../ide/choosing-a-deployment-method.md).  
  
 Примеры развертывания и рекомендации по устранению неполадок см. в разделе:  
  
-   [Примеры развертывания](../ide/deployment-examples.md).  
  
-   [Устранение неполадок C/C++ изолированных приложений и сборок Side-by-side](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>См. также  
 [Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Развертывание с помощью установщика Windows](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)